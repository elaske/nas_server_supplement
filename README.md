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

`ansible-galaxy install -r requirements.yml`

## Getting started
