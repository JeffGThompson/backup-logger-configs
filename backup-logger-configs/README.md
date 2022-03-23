# Ansible: basic server setup

[![Platform](https://img.shields.io/badge/platform-CentOS%206-lightgrey.svg?style=plastic)](#)
[![Platform](https://img.shields.io/badge/platform-RHEL%206-lightgrey.svg?style=plastic)](#)
[![Platform](https://img.shields.io/badge/platform-CentOS%207-lightgrey.svg?style=plastic)](#)
[![Platform](https://img.shields.io/badge/platform-RHEL%207-lightgrey.svg?style=plastic)](#)

This Ansible playbook backups logger configurations for Loggers and copies them over to the server you run the playbook on.

# Roles
This playbook consists of the following Ansible roles:

1. common
    - Runs the logger config backup commands and retrieves the file.

# Prerequisites

Ansible v2.0 or above is required to use this repo. To install Ansible, see [here](https://docs.ansible.com/ansible/intro_installation.html#installing-the-control-machine).


## Deploying the playbook

1. clone this repo: 

2. The IP address of the Logger(s) are in the file `inventory` under the correct group

3. Remove # on the left side of the IP address you wish to run the playbook on.

4. 
    A) Run the playbook as your adm account for Loggers connected to Active Directory:

    `$ ansible-playbook site.yml -i inventory -u jeffthompson -k -K  --ask-vault-pass`
    
    B) Run the playbook as the root user for Loggers not connected to Active Directory: 
   
    `$ ansible-playbook site.yml -i inventory -u root -k -K  --ask-vault-pass`

## Expected Outcome

See build status for what a successful execution of this playbook looks like. 


## Playbook Variables

A brief description of the variables used by this playbook.

The following variables are defined in `group_vars/all` with pre-set defaults that can be overridden:

| Variable | Explanation 
| -------- | -------- | 
| arcsight_home_path:   | Arcsight home path of the Logger. This path is different between appliances and standalone software.
