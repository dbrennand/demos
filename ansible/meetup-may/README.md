## Initialise Environment

```bash
uv sync
source .venv/bin/activate
for index in {1..2}; do
    orb create --user ubuntu ubuntu "ubuntu${index}"
done
```

## Ad-hoc Commands

```bash
ansible all -i inventory/inventory.yml -m command -a "useradd daniel"
ansible all -i inventory/inventory.yml -m command -a "lsblk"
```
