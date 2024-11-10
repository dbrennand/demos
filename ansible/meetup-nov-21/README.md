# Ansible Meetup - November 21 2024

This directory contains the Ansible content for my talk at the Ansible Meetup on November 21 2024.

## Talk Title

Infrastructure as Code - VPS provisioning with Ansible on Hetzner Cloud.

## Prerequisites

- A valid Hetzner Cloud account.
- A Hetzner Cloud API token.

## Dependencies

- See [requirements.yml](requirements.yml) for Ansible Galaxy dependencies.
- See [requirements.txt](requirements.txt) for Python dependencies.

## Usage

Populate the `hetzner_cloud_api_token` in [vars/main.yml](vars/main.yml) and `api_token` in [inventory/hcloud.yml](inventory/hcloud.yml) with your Hetzner Cloud API token. Make sure to encrypt them using `ansible-vault`.

```
git clone git@github.com:dbrennand/demos.git
cd demos/ansible/meetup-nov-21
python -m venv ~/.virtualenvs/$(basename $(pwd))
source ~/.virtualenvs/$(basename $(pwd))/bin/activate
pip install -r requirements.txt
ansible-galaxy install -r requirements.yml
ansible-playbook -i inventory/inventory.yml provision-playbook.yml
ansible-playbook -i inventory/hcloud.yml post-deploy-playbook.yml
ansible-playbook -i inventory/inventory.yml deprovision-playbook.yml
```
