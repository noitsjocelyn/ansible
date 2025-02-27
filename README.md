# Ansible playbooks for VMs

## Setup

### Local machine

Dependencies:

- `asdf`

Install tools:

```shell
asdf install
asdf reshim python
pip install -r requirements.txt
asdf reshim python
```

Create or link Ansible inventory file at `/etc/ansible/hosts`. E.g.

```shell
ln -s ./etc-ansible-hosts /etc/ansible/hosts 
```

### Remote servers

```shell
sudo dnf install python3-libdnf5
```

## Run the playbook

```shell
ansible-playbook dnf-vm-playbook.yaml --ask-become-pass 
```
