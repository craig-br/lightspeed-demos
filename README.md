# Ansible Lightspeed demo content

Compilation of Ansible Lightspeed demo content and examples.

## How do I configure Ansible Lightspeed?

Please use the following resources to install the Ansible VS Code extension and activate Ansible Lightspeed:

* [Ansible Lightspeed technical preview blog](https://www.ansible.com/blog/welcome-to-the-ansible-lightspeed-technical-preview)
* [Ansible Lightspeed technical preview video](https://youtu.be/yfXcGB7l0II)

Feel free to ask questions and provide feedback in the [Ansible Lightspeed Matrix Room](https://matrix.to/#/#lightspeed:ansible.com).

## ❗️Test before doing a demo

The IBM Watson Code Assistant model continues to improve and evolve with each release. This can result in generated suggestions that differ from the examples provided.

### Tested `solution_*.yml` Playbooks are available for each demo.

Tested Ansible Playbooks are available for each corresponding demo Playbook and start with the `solution_*.yml` prefix. For example, `solution_provision_azure_vm.yml`.  
Please use this to compare your generated suggestions before doing the demo.

## Demo content folder structure

The repository folder structure is as follows.

```bash
.
└── playbooks/
    └── <domain>/
        ├── demo_<playbook_name>.yml <-- Initial Ansible content for demo.
        └── prepare_<playbook_name>.yml <-- Used to prepare environment for demo.
        └── README.md <-- Step by step instructions.
        └── solution_<playbook_name>.yml <-- Tested Ansible content for comparison.
```

* `<domain>` - Ansible examples are sorted by domain. For example, the _cloud_ folder contains AWS, Azure, and Google Cloud content.
* `demo_<playbook_name>.yml` - Playbooks that start with `demo_*` are the initial Ansible example to use in the demo. For example, _demo_provision_ec2_instance.yml_ located in the _cloud/aws_ folder.
* `prepare_<playbook_name>.yml` - Playbooks that start with `prepare_*` prepares the environment for the demo.
* `README.md` - Contains a video and step-by-step instructions to prepare and perform the demo.
* `solution_<playbook_name>.yml` - Playbooks that start with `solution_*` have been tested with the latest version of the Ansible Lightspeed model. Use the tested Ansible content to compare your Ansible Lightspeed-generated outputs before the demo.

## Ansible Lightspeed demo list

Please refer to the `README.md` for each demo in the corresponding demo root folder for detailed demo instructions.

### Infrastructure

* [Install and configure Cockpit](./playbooks/infra/install_cockpit/README.md)
* [Install and configure web and database packages](./playbooks/infra/install_web_and_db/README.md)

### Cloud

* [Provision an AWS EC2 instance](./playbooks/cloud/aws/README.md)
* [Provision Azure resources and VM](./playbooks/cloud/azure/README.md)


---
