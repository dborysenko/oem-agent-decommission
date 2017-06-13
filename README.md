Oem Agent Decommission
=========

Role to decommission OEM agents. 

Requirements
------------

oem-agent-get-home role is required. get-fmw-domain-structure role might be required if you want to use that feature.

Role Variables
--------------

    OEM_URL: https://oem.example.com:8090/em # URL which can be used to login to OEM.
    OEM_PASSWORD: sysman password for OEM.
    OEM_HOST: oms1.example.com # One of OEM's nodes. Ansible host should have ssh-key based access to it.
    OEM_AGENT_PORT: 3872 # agent port
    

Dependencies
------------

dborysenko.oem-agent-get-home
dborysenko.get-fmw-domain-structure

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

site.yml
    
    - hosts: adminserver
      roles:
        - get-fmw-domain-structure

    - hosts: weblogic, adminsu, singlehosts
      gather_facts: False
      roles:
        - oem-agent-get-home
        - oem-agent-decommission

hosts


    [adminserver]
    adminserver.example.com
    
    [singlehosts]
    
    [weblogic]
    
    [all]
    
    [all:children]
    adminserver
    singlehosts
    weblogic
    
    [all:vars]
    ansible_user=dborysenko
    ansible_become_method=su
    ansible_become_exe=dzdo
    ansible_become_flags="su -"
    
    [deleg]
    oms1.example.com
    
    [deleg:vars]
    ansible_user=oracle

License
-------

BSD

Author Information
------------------

Dmytro Borysenko borysenus@gmail.com
