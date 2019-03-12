prepare-os
=========

Role used for initial configuration of managed hosts to allow connections from Ansible controller.

Requirements
------------

1. Allowed root ssh login
2. Has to be run with ANSIBLE_HOST_KEY_CHECKING variable set to 'false'


Role Variables
--------------


defaults/main.yml
----

    ansible_user_password: $6$mysecretsalt$MIJffjeQyfrKKrGkprGrDL/g2mCJa53koLmYQuuLmY9y37pDvGKPXU1Ov3RbMi.tpQ9cWvxAzUVtBLe7KrZoU.' #password
    ansible_user: root
    ansible_ssh_pass: password

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


    - hosts: all
      roles:
        - prepare-os
      handlers:
        - name: restart ssh
          service:
            name: sshd
            state: restarted
        

Run with:

    $ ANSIBLE_HOST_KEY_CHECKING=false ansible-playbook -i inventory_file playbook_file
    
    
License
-------

BSD

Author Information
------------------

www.b27.pl
