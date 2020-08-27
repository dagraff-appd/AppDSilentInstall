# AppDynamics Silent Install Prep

This repository is NOT support nor is it AppDynamics Official.

NO WARRANTY IS IMPLIED - USE AT YOUR OWN RISK

## Configuration

Prepare an inventory file

    all:
      vars:
        # platform_admin_port: 9191
        # platform_admin_database_port: 3377
        platform_admin_database_password: 
        platform_admin_database_root_password: 
        platform_admin_admin_password: 

        ec_admin_user: 
        ec_admin_password: 

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
