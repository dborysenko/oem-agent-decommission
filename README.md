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

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
