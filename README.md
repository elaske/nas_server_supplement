# nas-server-supplement

This repo contains an Ansible playbook that sets up a mini-pc running Ubuntu to be a server offloading applications usually running on the NAS.

Specifically, this is destined for a Zotac Zbox MI527 Nano backed by a Synology DS1812+.

## Prerequisites

On the remote system, the following things need to be installed / enabled for Ansible to work:

* OpenSSH Server (`openssh-server`)
* Python 2.x (`python-minimal` will suffice until Ansible catches up)

### Install Ansible

#### pip

`pip install ansible` (may need to run this as `sudo`)

### Install Requirements

`ansible-playbook -k -K install_roles.yml`

## Getting started

### Group Variables

* `nas_address` - hostname / IP of target NAS NFS mounting system 
* `plex_claim_code` - claim code to link up with plex.tv
* `plex_uid` - UID for `plex` user in `config/` directory.
* `plex_gid` - GID for `plex` user in the `config/` directory.

`plex_uid` and `plex_gid` are used to sync up with a `plex` (or "plex") user
already on the NFS mount's system.

### Vault

Obviously, you'll have to replace your `vault.yml` with your own secrets. You
can choose to either create your own `vault.yml` or simply replace the calls
to `vault_*` variables with the info you want to get things going.

### Running the Playbook

`ansible-playbook -i <YOUR HOST>, -k -K site.yml --ask-vault-pass`

*Note*: remove `--ask-vault-pass` if you are using plaintext secrets.
