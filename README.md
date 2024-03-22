# Ansible-Zero-to-Hero

# Ansible Overview and Usage Guide

## What is Ansible?

Ansible is an open-source automation tool that simplifies the management of infrastructure, configuration, and application deployment. It allows you to automate repetitive tasks, streamline workflows, and manage complex IT environments with ease.

## Key Features:

- **Agentless**: Ansible operates over SSH, eliminating the need for agent software on managed hosts.
- **Declarative**: Uses simple YAML syntax to describe the desired state of systems.
- **Orchestration**: Allows orchestration of tasks across multiple servers or devices simultaneously.
- **Extensibility**: Supports custom modules and plugins to extend functionality.
- **Idempotent**: Ensures that running a task multiple times produces the same result, reducing errors and inconsistencies.

## How to Use Ansible:

### 1. Installation:

- Ansible can be installed on various operating systems including Linux, macOS, and Windows Subsystem for Linux (WSL).
- Installation instructions can be found in the [official Ansible documentation](https://docs.ansible.com/ansible/latest/installation_guide/index.html).

### 2. Inventory:

- Ansible uses an inventory file to define the hosts it will manage.
- The inventory file can be a simple text file or dynamically generated using scripts or plugins.
- Example:

  ```ini
  [web_servers]
  server1.example.com
  server2.example.com

  [db_servers]
  server3.example.com
  ```

### 3. Playbooks:

Playbooks are YAML files that describe configurations and automation tasks.
Each playbook consists of one or more plays, which in turn contain tasks to be executed on hosts.

Example playbook:

```
- name: Install Apache web server
  hosts: web_servers
  tasks:
    - name: Install Apache
      apt:
        name: apache2
        state: present
      become: yes

```

### 4. Running Ansible:

Use the ansible-playbook command to execute playbooks against hosts.
Example command:

```
ansible-playbook -i inventory playbook.yml

```
