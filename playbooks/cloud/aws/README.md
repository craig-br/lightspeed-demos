# Provision an AWS EC2 instance using Ansible Lightspeed

[Demonstration video](../../../assets/img/provision_aws_instance.gif)

>❗️**Note**
>
>**Test the examples prior to performing a demo.**  
>
>
>Generative AI is dynamic in nature, and the Ansible Lightspeed with IBM Watson Code Assistant model continues to improve and evolve with each release.  
>
>This can result in receiving suggestions that differ from the examples provided.

## Overview

Provisions an AWS instance using pre-existing variables.

### Step 1

#### Uncomment and generate task first task description `- name: Create t3.medium instance`

- Used natural language prompt to generate syntactically correct Ansible task.
- Suggestion incorporated Ansible best practices and used Fully Qualified Collection Name (FQCN).
- Suggestion provides good variable examples for module arguments.

### Step 2

#### Update first task description `- name: Create t3.medium instance using instance_config var`

- Ansible Lightspeed used the updated natural language prompt and infused the `instance_config` variable into the suggestion.

### Step 3

#### Uncomment and generate task `- name: Create var called instance_public_ip from the ec2 instance public ip address`

- The suggestion used the `register` variable name from the previous task.
- Ansible Lightspeed generated a complex variable using a simple prompt - `from the ec2 instance public ip address`.

### Step 4

#### Uncomment and generate task `- name: Print that variable`

- Ansible Lightspeed used the previous variable name from a generic prompt.
