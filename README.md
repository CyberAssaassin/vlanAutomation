# Automated VLAN Creator (Ansible + YAML)

An automated network configuration project using Ansible to deploy and manage VLANs across Cisco IOS network switches with full idempotency.

## Project Structure
* `inventory.yaml`: Defines target switches, connection plugins (`network_cli`), and network OS drivers (`cisco.ios.ios`).
* `vars.yaml`: Contains structured YAML data defining the VLAN IDs and names.
* `vlan_playbook.yaml`: The Ansible playbook that reads variables, loops through them, and applies configuration via the `cisco.ios.ios_vlans` module.

## Requirements
* Ansible Core
* `cisco.ios` collection (`ansible-galaxy collection install cisco.ios`)

## Usage / Dry Run
To run a dry-run check against your inventory configuration:
```bash
ansible-playbook -i inventory.yaml vlan_playbook.yaml --check
