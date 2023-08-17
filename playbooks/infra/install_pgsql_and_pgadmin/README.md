# Install and configure PostgreSQL and PGAdmin container using Ansible Lightspeed

## Overview

The demo consists for two Ansible Playbooks that performs the following tasks respectively:

- Installs `postgresql-server`, initializes the database, and starts and enables the `postgresql` service.
- Uses `podman` to configure and run the **dpage/pgadmin4** as a service.

This demo illustrates the following Ansible Lightspeed features:

- Translating easy-to-understand prompts into syntactically correct Ansible content without needing in depth knowledge of the automated technology.
- Using keywords, such us `....using X var`, in prompts to obtain desired suggestions.
- Using the full YAML file context to generate Ansible content with best practices.

## Demo preparation

1. Install the VS Code extension and activate Ansible Lightspeed using resources in the [getting started guide](../../../GETTING_STARTED.md).
2. If not running this example in the Ansible self-paced labs environment, create an Ansible Inventory file with `webservers` and `databases` Ansible inventory groups with the corresponding Linux target host(s) details.

[Example Ansible inventory file](./inventory/inventory.yml)

```yaml
---
all:
  children:
    webservers:
      hosts:
        webserver-01:
          ansible_host: example-host # Update this to your target host.
    databases:
      hosts:
        database-01:
          ansible_host: example-host # Update this to your target host.
  vars:
    ansible_ssh_private_key_file: "example-key" # Update this to your target host.
    ansible_user: example-user # Update this to your target host.
    ansible_host_key_checking: false
```

## Tested content

The model continues to improve and evolve with each release and generated suggestions could differ from the examples provided. Tested content is available in the corresponding [`solution_install_cockpit.yml`](./solution_install_cockpit.yml) Playbook.

## Running the demo

### First Playbook `demo_install_pgsql.yml`

Run the steps below in the [./playbooks/infra/install_pgsql_and_pgadmin//demo_install_pgsql.yml](./demo_install_pgsql.yml) Ansible Playbook.

### Step 1

#### Uncomment and generate first task `- name: Install httpd package`

- Used natural language prompt to generate syntactically correct Ansible Playbook task.
- Suggestion incorporated Ansible best practices and used Fully Qualified Collection Name (FQCN).

### Step 2

#### Uncomment and generate task `- name: Copy httpd.conf.j2 template to /etc/httpd/conf/`

- Ansible Lightspeed suggestion used best practices and defined the file permissions, owner and group in the module arguments.

### Step 3

#### Uncomment and generate task `- name: Start and enable httpd service`

- Ansible Lightspeed used natural language prompt and added `state: started` and `enabled: true` module arguments based on `Start and enable...` in the Ansible task description.

### **In the second Ansible play**

### Step 4

#### Uncomment and generate task `- name: Install postgresql-server`

### Step 5

#### Uncomment and generate task `- name: Run postgresql setup`

- Ansible Lightspeed used an easy-to-understand natural language prompt and suggested the correct, more complex PostgreSQL CLI command to initiate the database.
- Ansible Lightspeed used best practices and kept the task idempotent by including `creates: /var/lib/pgsql/data/postgresql.conf` in the suggestion.

### Step 6

#### Uncomment and generate task `- name: Start and enable postgresql service`

---
