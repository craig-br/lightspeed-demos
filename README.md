# Ansible Lightspeed with IBM Watson Code Assistant demo content

Compilation of Ansible Lightspeed with IBM Watson Code Assistant demo content and examples.

## How do I configure Ansible Lightspeed?

Please use the following resources to install the Ansible VS Code extension and activate Ansible Lightspeed:

[Ansible Lightspeed technical preview blog](https://www.ansible.com/blog/welcome-to-the-ansible-lightspeed-technical-preview)

* Covers setting up the Ansible VS Code extension and activating Ansible Lightspeed.

[Ansible Lightspeed technical preview video](https://youtu.be/yfXcGB7l0II)

* This video shows how to install the Ansible VS Code extension and activate Ansible Lightspeed.

[Ansible Lightspeed Matrix Room](https://matrix.to/#/#lightspeed:ansible.com)

* Feel free to ask questions and provide feedback in the Ansible Lightspeed Matrix Room.

## Test the examples prior to performing a demo

The Ansible Lightspeed with IBM Watson Code Assistant model continues to improve and evolve with each release.  

This can result in generated suggestions that differ from the examples provided.

### Tested content is available in the corresponding `solutions` folder

Tested Ansible content is available in the `solutions` folder for each demo. Please use this to compare your generated suggestions to the tested Ansible content.

## Demo content folder structure

The repository folder structure is as follows.

```bash
.
└── playbooks/
    └── <domain>/
        ├── <demo_content>.yml <-- Initial Ansible content for demo.
        └── solutions/
            └── <demo_content>.yml <-- Tested Ansible content for comparison.
```

* `<domain>` - Ansible examples are sorted by domain. For example, the _cloud_ folder contains AWS, Azure, and Google Cloud content.
* `<demo_content>.yml` - This refers to the initial Ansible example to use in the demo. For example, _provision_ec2_instance.yml_ located in the _cloud/aws_ folder.
* `solutions/<demo_content>.yml` - Ansible content that’s been tested with the latest version of the Ansible Lightspeed model. Use the tested Ansible content to compare your Ansible Lightspeed-generated outputs before the demo.

## Ansible Lightspeed demo list

Please refer to the `README.md` for each demo in the corresponding demo root folder for detailed demo instructions.

### Infrastructure

### Cloud

* [Provision an AWS EC2 instance](./playbooks/cloud/aws/README.md)

---
