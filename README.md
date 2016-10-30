# MailHops API Ansible Playbooks

<img src="https://www.mailhops.com/images/logos/logo.png" alt="MailHops logo" title="MailHops" align="right" />

Start off with a CentOS 7 EC2 instance from the AWS Marketplace

Edit the security group:
* Allow inbound port 80
* Allow inbound Mongo 27017 from hosts 10.0.0.0/16

**available tags**
* monitoring
* code_only

```sh
# On Mac
brew install ansible

# Edit the inventory file
cp inventory.sample inventory
vi inventory

# Edit defaults
vi roles/mailhops-api/defaults/main.yml

# Install on CentOS 7 Instance
ansible-playbook -i inventory mailhops.yml

# Install on CentOS 7 Instance with tags
ansible-playbook -i inventory mailhops.yml --tags code_only --skip-tags monitoring
```
