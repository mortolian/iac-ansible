# Redhat Ansible Automation

The purpose of this repo is to gather all my knowledge and build up a small library of repetative work I do with Ansible. The idea is to get better over time and do more complex configurations while saving a lot of time.

What is really nice about Ansible is that you can use Python to do more
scripted and complex work.

## Install Ansible on Macbook Using Homebrew

```bash
brew install ansible
```

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

To run playbooks against hosts without having to enter the password over and over, you can
setup a passwordless ssh key login using the command below from the host you are planning
to run ansible from.

```bash
ssh-copy-id {ip/host address}
```

## Running Playbooks

```bash
ansible-playbook playbooks/update-ubuntu-server.yml -i inventory.yml -K
ansible-playbook playbooks/update-pi-hole.yml -i inventory.yml -K
ansible-playbook playbooks/update-proxmox-node.yml -i inventory.yml -K
```

The `-K` option will allow for the `sudo` user password to be prompted for each
host in the inventory.

## References

- <https://docs.ansible.com/>
- <https://www.ansible.com/>
- <https://www.digitalocean.com/community/tutorials/how-to-set-up-ansible-inventories>

## Contribution

Anyone can contribute by submitting a pull request and you are welcome to use the
repo in any way you like.

### Some Todos

- Find a way to automate Ansible tasks from a trusted host and user.
- Create an inventory template file for a single host. Have all the inventory options available and uncomment only the ones you need.
- Document automation options with make file, cron jobs etc.

### Ideas for playbooks

- Playbook which changes passwords for a large number of machines when a user exists. <https://www.howtouselinux.com/post/change-user-password-with-ansible>
