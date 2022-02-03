# ctf-vps
An Ansible playbook for Debian-based systems to use the Kali repos and install tools for CTFs.

## Requirements
Since Kali is Debian-based, only use on a Debian-based system!

**Note: The Kali repos are not added to the existing ones, but replace them!**

This is intended to be used with ansible-pull, so the following programs are needed:

- ansible
- git

## Usage
The playbook creates a user who is a member of the sudo group. For this, it expects three environment variables to be set:

- `ANSIBLE_USER` for his username
- `ANSIBLE_USERPASS` for his password
- `ANSIBLE_PUBKEY` for the public SSH key that will be added to his authorized_keys file

They can be set like this:
```sh-session
export ANSIBLE_USER = username
export ANSIBLE_USERPASS = mypassword
export ANSIBLE_PUBKEY = 'ssh-ed25519 AAAAZ5MaaeXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXrAPrd3puF2vfpX user@host'
```

Then pull the playbook from Github and execute it:
```sh-session
ansible-pull -U https://github.com/iougiri/ctf-vps.git
```

