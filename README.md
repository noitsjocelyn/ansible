# Ansible playbooks for VMs

## Setup

### Local machine

Dependencies:

- `asdf`

Install tools:

```sh
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

```sh
ln -s ./etc-ansible-hosts.yaml /etc/ansible/hosts 
```

### Remote servers

#### Fedora config

- I use the "Network Installer" from [Fedora Alt Downloads](https://alt.fedoraproject.org)
- I use the "Custom Install" packages choice with only Standard and Guest Agents selected as extra
- Tested on Fedora 41 and 42

#### Pre-playbook setup
 
Configure remote server for SSH login (e.g. add your login key for the admin VM user).

Install `python3-libdnf5`:

```sh
sudo dnf install python3-libdnf5
```

Set your hostname, if needed:

```sh
sudo hostnamectl hostname [your-hostname.lan]
sudo shutdown -r now
```

## Run the playbook

```sh
ansible-playbook fedora-vm-playbook.yaml --ask-become-pass
```
