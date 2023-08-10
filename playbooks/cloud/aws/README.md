# Provision an AWS EC2 instance using Ansible Lightspeed

## Configure and activate Ansible Lightspeed

Install the VS Code extension and activate Ansible Lightspeed using resources in the [getting started guide](../../../getting_started.md).

### ❗️ Test suggestions using the corresponding Playbook in the `solutions` folder

The Ansible Lightspeed model continues to improve with each release and generated suggestions may differ from the examples provided.  
Tested Ansible content is available in the [solutions](./solutions/) folder. Please use this to compare your generated suggestions to the tested Ansible content.

## Overview

This demo provisions an AWS EC2 instance using pre-existing variables.

![](../../../assets/img/lightspeed_provision_aws_instance.gif)

## Demo preparation

1. Configure your AWS credential environment variables as outlined in the [Ansible AWS guide](https://docs.ansible.com/ansible/latest/collections/amazon/aws/docsite/guide_aws.html#authentication).
2. Run the [./prepare/prepare_provision_ec2_instance.yml](./prepare/prepare_provision_ec2_instance.yml) Playbook to create the required AWS demo resources before running the `provision_aws_instance.yml` Playbook.

### Accessing the instance

1. The `./prepare/prepare_provision_ec2_instance.yml` creates a temporary SSH private .pem key file in the `./playbooks/cloud/aws/` folder to access the instance.
2. An example inventory is located the [inventory folder](./inventory/).

## Running the demo

### Ansible demo content

#### Initial Ansible Playbook

[./playbooks/cloud/aws/provision_aws_instance.yml](./provision_ec2_instance.yml)

#### Tested Ansible Playbook

[./playbooks/cloud/aws/solutions/provision_aws_instance.yml](./solutions/provision_ec2_instance.yml)

Run the steps below in the [./playbooks/cloud/aws/provision_aws_instance.yml](./provision_ec2_instance.yml) example Ansible Playbook.

### Step 1

#### Uncomment and generate task `- name: Gather secgroup-lightspeed EC2 security group info`

- Used natural language prompt to generate syntactically correct Ansible Playbook Task.
- Suggestion incorporated Ansible best practices and used Fully Qualified Collection Name (FQCN).

### Step 2

#### Uncomment and generate task `- name: Create 'security_group' var from secgroup-lightspeed group_id`

- Used the Playbook context to use AWS Ansible modules in the suggestion.
- Used natural language to generate the `security_group` variable using the correct variable keys.

### Step 3

#### Uncomment and generate task `- name: Gather subnet info tag:Name subnet-lightspeed`

- Used `tag:Name subnet-lightspeed` in the prompt to use the correct AWS filter.

### Step 4

#### Uncomment and generate task `- name: Create vpc_subnet_id var`

- Used `tag:Name subnet-lightspeed` in the prompt to use the correct AWS filter.

### Step 5

#### Uncomment and generate task `Create EC2 t2.micro instance`

- Suggestion provides good variable examples for module arguments.

### Step 6

#### Remove the previous task and generate a new task with  `- name: Create EC2 t2.micro instance using ec2_config var`

- Ansible Lightspeed used the updated natural language prompt and referenced the `ec2_config` variable in the suggestion.

---
