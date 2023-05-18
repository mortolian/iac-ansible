# Ansible Template

## Configure Inventory

Rename the `inventory.yml.example` file to `inventory.yml` and setup all the hosts as indicated in the template.

To get a list of the inventory hosts.

```bash
ansible-inventory -i inventory.yml --list
```

To test the inventory you can run the following commands.

```bash
ansible all -i inventory.yml -m ping
```

## Install SSH keys To Run Commands Without A Password

```bash
ssh-copy-id {ip/host address}
```

## Running Playbooks

```bash
ansible-playbook playbooks/update-ubuntu-server.yml
```

## References

- <https://docs.ansible.com/>
- <https://www.ansible.com/>
- <https://www.digitalocean.com/community/tutorials/how-to-set-up-ansible-inventories>
