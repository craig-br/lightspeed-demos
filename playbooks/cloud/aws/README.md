# Provision an AWS EC2 instance using Ansible Lightspeed

## Configure and activate Ansible Lightspeed

Install the VS Code extension and activate Ansible Lightspeed using resources in the [getting started guide](../../../getting_started.md).

### ❗️ Test suggestions using the corresponding `solution_*.yml` Playbook

The Ansible Lightspeed model continues to improve with each release and generated suggestions may differ from the examples provided.  
Tested Ansible content starts with the `solution_*.yml` prefix. For example, `solution_provision_ec2_instance.yml` Please use this to compare your generated suggestions to the tested Ansible content.

## Overview

This demo provisions an AWS EC2 instance using pre-existing variables.

![](../../../assets/img/lightspeed_provision_aws_instance.gif)

## Demo preparation

1. Configure your AWS credential environment variables as outlined in the [Ansible AWS guide](https://docs.ansible.com/ansible/latest/collections/amazon/aws/docsite/guide_aws.html#authentication).
2. Run the [./prepare_ec2_environment.yml](./prepare_ec2_environment.yml) Playbook to create the required AWS demo resources before running the `demo_provision_aws_instance.yml` Playbook.

### Accessing the instance

1. The `./prepare_ec2_environment.yml` creates a temporary SSH private .pem key file in the `./playbooks/cloud/aws/files` folder to access the instance.
2. An example inventory is located the [inventory folder](./inventory/).

## Running the demo

### Ansible demo content

#### Initial Ansible Playbook

[./playbooks/cloud/aws/demo_provision_ec2_instance.yml](./demo_provision_ec2_instance.yml)

#### Tested Ansible Playbook

[./playbooks/cloud/aws/solution_provision_ec2_instance.yml](./solution_provision_ec2_instance.yml)

## Running the demo

Run the steps below in the [./playbooks/cloud/aws/demo_provision_aws_instance.yml](./demo_provision_ec2_instance.yml) example Ansible Playbook.

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

#### Uncomment and generate task `Create t2.micro instance`

- Suggestion provides good variable examples for module arguments.

### Step 6

#### Remove the previous task and generate a new task with  `- name: Create t2.micro instance using ec2_config var`

- Ansible Lightspeed used the updated natural language prompt and referenced the `ec2_config` variable in the suggestion.

---
