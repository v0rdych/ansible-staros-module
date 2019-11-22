Role Name
=========

staros-module for Cisco StarOS devices management

Requirements
------------

No specific requirements are used

Role Variables
--------------

Maybe variables will be used later

Dependencies
------------

Depends on basic network_cli connection

Example Playbook
----------------


    - connection: network_cli
      hosts: saegwtest
      gather_facts: false
      roles:
        - role: staros-module
      - name: ensure that test.acl in saegw context  contains 'redirect css service CSS any' string
        staros_config:
          diff_ignore_lines:
            - .*encrypted key.*
            - .*ssh key.*
          commands:
            - redirect css service CSS any
          parents:
            - config
            - context saegw
            - ip access-list test.acl

License
-------

BSD

Author Information
------------------

https://github.com/v0rdych/ansible-staros-module
