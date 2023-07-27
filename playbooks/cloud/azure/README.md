# Provision Azure resources and virtual machine

## Configure and activate Ansible Lightspeed

Install the VS Code extension and activate Ansible Lightspeed using resources in the [getting started guide](../../../getting_started.md).

## ❗️Note - Test the examples before doing a demo

The model continues to improve and evolve with each release and generated suggestions could differ from the examples provided.

### Tested content is available in the corresponding `solutions` folder

Tested Ansible content is available in the [solutions](./solutions/) folder. Please use this to compare your generated suggestions to the tested Ansible content.

## Overview

This demo provisions multiple Azure resources, such as a resource group, networking, security groups, and an Azure virtual machine.  

This demo is more advanced as it has several tasks and requires manual changes to some of the suggestions. However, it's a good example of how Ansible Lightspeed uses previous task patterns, previously generated content, and variables in later suggestions.

An example Azure inventory is available in the [inventory](./inventory/) folder. It uses the [Azure Resource Manager inventory plugin](https://docs.ansible.com/ansible/latest/collections/azure/azcollection/azure_rm_inventory.html).

![](../../../assets/img/lightspeed_provision_azure_resources.gif)

## Demo preparation

1. Use environment variables to configure your Azure credentials as outlined in the [Ansible Microsoft Azure guide](https://docs.ansible.com/ansible/latest/scenario_guides/guide_azure.html#using-environment-variables).
2. Edit the `key_data:` entry in `vm_instance` variable with the location of your public SSH key file:

```yaml
  vars:
    vm_instance:
      image:
        offer: RHEL
        publisher: RedHat
        sku: 9-lvm
        version: latest
      network_interfaces:
        - nic-lightspeed
      ssh_public_keys:
        - path: /home/rhel/.ssh/authorized_keys
          key_data: "{{ lookup('file', 'Your Azure public SSH key file') }}"
      ssh_password_enabled: false
      vm_size: Standard_DS2_v2
      admin_username: rhel
```

## Running the demo

### Ansible demo content

#### Initial Ansible Playbook to use in the demo

[./playbooks/cloud/azure/provision_azure_resources.yml](./provision_azure_resources.yml)

#### Tested Ansible Playbook to compare your results

[./playbooks/cloud/azure/solutions/provision_azure_resources.yml](./solutions/provision_azure_resources.yml)

Run the steps below in the initial [./playbooks/cloud/azure/provision_azure_resources.yml](./provision_azure_resources.yml) example Ansible Playbook.

### Step 1

#### Uncomment and generate the first task `- name: Create resource group called rg-lightspeed`

- Suggestion used the Playbook name, `Create Azure VM`, to know which Ansible module to use.
- Used natural language prompt to generate syntactically correct Ansible Playbook task.
- Suggestion incorporated Ansible best practices and used Fully Qualified Collection Name (FQCN).
- Used `...called rg-lightspeed` in the task description to correctly name the Azure resource group.

### Step 2

#### Uncomment and generate task `- name: Create virtual network called vnet-lightspeed`

>❗️Note  
>Change the `address_prefixes: 10.0.0.80/16` to `address_prefixes: 10.0.0.0/16`

- Ansible Lightspeed demonstrated continuity by using the `rg-lightspeed` Azure resource group created in the previous task in the suggestion.

### Step 3

#### Uncomment and generate task `- name: Add subnet called subnet-lightspeed`

>❗️Note  
>Change the `address_prefix: 10.0.1.48/24` to `address_prefix: 10.0.1.0/24`

- Ansible Lightspeed used `vnet-lightspeed`, created in the previous task, in the suggestion.

### Step 4

#### Uncomment and generate task `- name: Create public IP address called ip-lightspeed`

- Ansible Lightspeed used the `rg-lightspeed` Azure resource group created in a previous task.

### Step 5

#### Uncomment and generate task `- name: Create azure_public_ip var`

- Ansible Lightspeed used the `azure_public_ip` variable name to know that the user wanted the public IP address.
- The suggestion used the previous register variable, `output_ip_address`, and the correct variable key `.state.ip_address`.

### Step 6

#### Uncomment and generate task `- name: Print azure_public_ip var`

### Step 7

#### Uncomment and generate task `- name: Create Network Security Group that allows SSH`

- The suggestion used `...that allows SSH` in the task description to create the correct security group rule.
- Ansible Lightspeed used the same naming convention, `xyz-lightspeed` used in the previous tasks - `network-securitygroup-lightspeed`.

### Step 8

#### Uncomment and generate task `- name: Create virtual network interface`

- Ansible Lightspeed used all the previously created Azure objects e.g. `ip-lightspeed` and `subnet-lightspeed` in the suggestion.
- The suggestion used the correct naming convention - `nic-lightspeed`.

### Step 9

#### Uncomment and generate task `- name: Create VM using vm_instance var`

- Ansible Lightspeed used the `vm_instance` variable fields in the suggestion as requested in the task description, `...using vm_instance var`.
- The suggestion used the correct naming convention - `vm-lightspeed`.
- Ansible Lightspeed demonstrated continuity by using `rg-lightspeed` and `eastus` in the suggestion.

---
