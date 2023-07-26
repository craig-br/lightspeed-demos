# Provision an AWS EC2 instance using Ansible Lightspeed

## ❗️Note

### Test the examples prior to performing a demo

The Ansible Lightspeed with IBM Watson Code Assistant model continues to improve and evolve with each release.  

This can result in generated suggestions that differ from the examples provided.

### Tested content is available in the corresponding `solutions` folder

Tested Ansible content is available in the [solutions](./solutions/) folder. Please use this to compare your generated suggestions to the tested Ansible content.

## Overview

This demo provisions an AWS EC2 instance using pre-existing variables.

![](../../../assets/img/provision_aws_instance.gif)

## Demo preparation

1. Install the Ansible VS Code extension and activate Ansible Lightspeed. Below are resources to get started:

- [Ansible Lightspeed Technical Preview blog](https://www.ansible.com/blog/welcome-to-the-ansible-lightspeed-technical-preview).
-  [Ansible Lightspeed Technical Preview video](https://youtu.be/yfXcGB7l0II).



2. Use environment variables to configure your AWS credentials as outlined in the [Ansible documentation](https://docs.ansible.com/ansible/latest/collections/amazon/aws/docsite/guide_aws.html#authentication).
3. Edit the `instance_config` variable keys with your AWS details:

- `key_name`
- `vpc_subnet_id`
- `security_group`

```yaml
  vars:
    instance_config:
      name: lightspeed-instance-01
      tags:
        function: aws-cloud-ops
      key_name: 'Your AWS keypair name'
      image_id: ami-016eb5d644c333ccb # RHEL 9 us-east-1
      vpc_subnet_id: 'Your VPC subnet ID'
      security_group: 'Your security group'
      region: us-east-1
```
## Running the demo

### Ansible demo content

#### Initial Ansible Playbook

[./playbooks/cloud/aws/provision_aws_instance.yml](./provision_ec2_instance.yml)

#### Tested Ansible Playbook

[./playbooks/cloud/aws/solutions/provision_aws_instance.yml](./solutions/provision_ec2_instance.yml)

Run the steps below in the [./playbooks/cloud/aws/provision_aws_instance.yml](./provision_ec2_instance.yml) example Ansible Playbook.

### Step 1

#### Uncomment and generate task first task description `- name: Create t3.medium instance`

- Suggestion used the Playbook name, `AWS Cloud Operations`, to know which Ansible module to use.
- Used natural language prompt to generate syntactically correct Ansible Playbook Task.
- Suggestion incorporated Ansible best practices and used Fully Qualified Collection Name (FQCN).
- Suggestion provides good variable examples for module arguments.

### Step 2

#### Update first task description `- name: Create t3.medium instance using instance_config var`

- Ansible Lightspeed used the updated natural language prompt and referenced the `instance_config` variable into the suggestion.

### Step 3

#### Uncomment and generate task `- name: Create var called instance_public_ip from the ec2 instance public ip address`

- Ansible Lightspeed kept continuity and used the `register` variable name from the previous task in the suggestion.
- Ansible Lightspeed generated a complex variable using a simple prompt - `from the ec2 instance public ip address`.

### Step 4

#### Uncomment and generate task `- name: Print that variable`

- Ansible Lightspeed used the previous variable name from a generic prompt.

---
