ansible-oracle-linux-oscap
=========

Ansible role to execute OSCAP (OpenSCAP) scan on multiple Oracle Linux machines. Do not use this role on engineered systems like (PCA, ZFS and Exadata).

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

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

BSD

Author Information
------------------

Arun Yadav
(www.itnoesis.com)
