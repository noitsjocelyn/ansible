# Ansible playbooks for VMs

## Setup

### Local machine

Dependencies:

- `asdf`

Install tools:

```shell
# Install Python version
asdf install
asdf reshim python

# Install Ansible
pip install --upgrade pip
pip install -r requirements.txt
asdf reshim python
```

Create or link Ansible inventory file at `/etc/ansible/hosts`.

E.g.:

```shell
ln -s ./etc-ansible-hosts /etc/ansible/hosts 
```

### Remote servers

Configure remost server for SSH login (e.g. add your login key for the VM user).

Install `python3-libdnf5`:

```shell
sudo dnf install python3-libdnf5
```

Set your hostname, if needed:

```shell
sudo hostnamectl hostname [your-hostname.lan]
sudo shutdown -r now
```

## Run the playbook

```shell
ansible-playbook fedora-vm-playbook.yaml --ask-become-pass
```
