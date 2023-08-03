# Ansible Playbook for Deploying Apache Service

## Introduction

This Ansible playbook automates the deployment of the Apache HTTP server on target servers.

## Prerequisites

Before running this playbook, ensure the following:

1. Ansible is installed on your local machine.
2. You have SSH access to the target servers with appropriate privileges.

## Running the Playbook

1. Save the playbook in a file named `apache.yaml`.
2. Create an inventory file named `inventory.ini` and specify the target hosts in it.
3. Execute the following command in the terminal:

```bash
ansible-playbook -i inventory.ini apache.yaml
```
Ansible will connect to the target servers, install Apache (if not already installed), start the Apache service, and enable it to start on boot.

4. Likewise, if you wish to uninstall the apache service, run the `uninstall_apache.yml` playbook using the following command:

```bash
ansible-playbook -i inventory.ini uninstall_apache.yml
```

## Notes

- This playbook assumes that the target servers have internet access to download packages from the repositories during the installation process.
- The playbook uses the `become: yes` directive to elevate privileges (sudo) while executing tasks on the target servers.
- Ensure that you have SSH access to the target servers and the necessary permissions to perform installations and start/stop services.
- It is recommended to test the playbook in a controlled environment before deploying it to production servers. Always have backups and proper version control for critical systems.
