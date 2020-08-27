# AppDynamics Silent Install Prep

This repository is NOT support nor is it AppDynamics Official.

NO WARRANTY IS IMPLIED - USE AT YOUR OWN RISK

## Configuration

Prepare an inventory file

    all:
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
