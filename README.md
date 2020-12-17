# AppDynamics Silent Install Prep

This repository is NOT support nor is it AppDynamics Official.

NO WARRANTY IS IMPLIED - USE AT YOUR OWN RISK

## Configuration

Prepare an inventory file

    all:
      vars:
        # This is the name of the target platform credential vault
        # It expects you will have a file "{{ vault_id }}-vault.yaml" existing in the root of the project
        # Otherwise it will attempt to find "default-vault.yaml"
        # Errors will be ignored
        # Follow the vault.yaml.template file for sensitive credential storage
        # 
        # vault_id: 

        # platform_admin_port: 9191
        # platform_admin_database_port: 3377
        platform_admin_database_password: 
        platform_admin_database_root_password: 
        platform_admin_admin_password: 

        ec_admin_user: 
        ec_admin_password: 

        # May be one of demo (default), small, medium, large
        # controller_profile: demo
        # May be one of dev (default), prod
        # events_service_profile: dev

        controller_admin_username: 
        controller_admin_password: 
        controller_root_user_password: 
        controller_database_root_password: 
        controller_database_user_password: 
      children:
          enterprise_console:
            hosts:
              ec:
                ansible_host:
          controller:
            hosts:
              primary_controller:
                  ansible_host: 
              # This is optional 
              secondary_controller:
                  ansible_host: 
          events_service:
            hosts:
              events_service1:
                ansible_host: 
              events_service2:
                ansible_host: 
              events_service3:
                ansible_host: 

## After execution

The playbook will generate two template files in addition to configuring the system and users for installation.
The 'silent.varfile' can be used with the command ./platform...sh -q -varfile silent.varfile to install the EC
The 'silent_install.sh' will execute the installation of the controller and events service nodes.
