# Ansible Meetup - May 2025

This directory contains the Ansible content for my talk at the Ansible Meetup in May 2025.

## Talk Title

Ansible 101 - Getting Started.

## Prerequisites

- [`uv`](https://docs.astral.sh/uv/)
- [OrbStack](https://orbstack.dev/)

## Dependencies

See [pyproject.toml](pyproject.toml) for Python dependencies.

## Usage

### Initialise the Environment

```bash
# Install dependencies
uv sync
# Activate Python Virtual Environment
source .venv/bin/activate
# Create VMs using OrbStack
orb create --user ubuntu ubuntu ubuntu1
orb create --user ubuntu ubuntu ubuntu2
```

### View Inventory

```bash
ansible-inventory -i inventory/inventory.yml --list
```

### Ad-hoc Commands

```bash
ansible all -i inventory/inventory.yml -m command -a "useradd daniel"
ansible all -i inventory/inventory.yml -m command -a "lsblk"
```

### Playbooks

```bash
ansible-playbook -i inventory/inventory.yml example-playbook.yml
```
