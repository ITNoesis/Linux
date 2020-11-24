ansible-oracle-linux-oscap
=========

Ansible role to execute OVAL (Open Vulnerability and Assessment Language) and XCCDF (Extensible Configuration Checklist Description Format) based OSCAP (OpenSCAP) scan on multiple Oracle Linux machines. 

Use this role to:
1. Install the latest oscap packages
2. Scan Oracle Linux systems
3. Collect all the html and xml reports at a centralized location (ansible controller)

By default, this role scans the systems based on standard profile however, the behaviour can be controlled by the variable "oscap_profile".

IMP: Do not use this role on engineered systems like (PCA, ZFS and Exadata).

Samples:
------------
OVAL Scan results:
![alt text](https://github.com/ITNoesis/Linux/blob/master/ansible-oracle-linux-oscap/tests/OVAL_Results1.PNG?raw=true)
![alt text](https://github.com/ITNoesis/Linux/blob/master/ansible-oracle-linux-oscap/tests/OVAL_Results2.PNG?raw=true)

OSCAP XCCDF Scan results:
![alt text](https://github.com/ITNoesis/Linux/blob/master/ansible-oracle-linux-oscap/tests/SCAP1.PNG?raw=true)
![alt text](https://github.com/ITNoesis/Linux/blob/master/ansible-oracle-linux-oscap/tests/SCAP2.PNG?raw=true)

Role Variables
--------------

This role requires the following variables which are defined in defaults/main.yml.

      oscap_profile: standard
      oscap_policy_oel7: ssg-rhel7-xccdf
      oscap_policy_oel6: ssg-rhel6-xccdf
      local_report_dir: /tmp/oscap-scan-latest
      Central_report_dir: /mnt/sec_scan
      scap_config_dir: /usr/share/xml/scap/ssg/content
      ansible_python_interpreter: "/usr/bin/python"
      central_server: <FQDN of ansible controller server>

Dependencies
------------

OVAL definitions file (com.oracle.elsa-all.xml).
#TODO
Add code to download the definitions file, controlled by download flag.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-oracle-linux-oscap }

License
-------

BSD (Refer to the root folder for details)

Author Information
------------------

Arun Yadav
(www.itnoesis.com)
