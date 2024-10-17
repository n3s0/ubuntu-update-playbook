# Ubuntu Update Playbook
---

## Summary
---

Simple Ansible playbook for updating Ubuntu Servers. But, this will probably work
on Ubuntu Desktop as well.

The objective of this playbook is to have the capability to update multiple
instances of Ubuntu Server at a time. You just add the server to your inventory
file and off you go.

I've been meaning to automate tasks in multiple ways for various servers for a
long time. So, I thought this would be the best starting point for this.

## CAUTION
---

One thing I wouldn't recommend doing is running this Ansible playbook on servers
that need to be updated in a specific order. As I learn more about Ansible
playbooks, I will try to figure out a way to prioritize or create a dependancy
for updating servers in a certain order. I'm thinking about this mostly for
those that have database replicas that need to be rebooted at the same time.

For now. Updates will be performed in order or all at once as listed in the
inventory file.

## Confirmed Tests
---

This playbook has successfully run on the following versions of Ubuntu.

- Ubuntu Server 24.04 LTS amd64

## What The Playbook Does
---

This playbook will perform the following tasks on the servers in the hosts file.

1. Update the apt cache.
2. Perform a dist upgrade and force updates.
3. Reboot the server and confirm it comes back up.

This is a very simple script for when you don't mind checking services later.
One thing I would recommend post-run is to check the configuration and the
status of your servers when the playbook completes.

## Clone Repository
---

Repository can be cloned using the following command.

```sh
git clone https://github.com/n3s0/ubuntu-update-playbook.git
```

## Adding Hosts
---

Hosts can be added to the hosts file. This is also where you will provide the
user name you intend to login to your servers with. One recommendation I have
for this is to copy the SSH public keys ahead of time and then run the playbook.

## Running The Playbook
---

To run the playbook please issue the following command.

```sh
anisble-playbook -i hosts ubuntu-update.yml
```

## Troubleshooting
---

One good tip should the script fail is to make sure you have the servers public
SSH key. I didn't add anything for password or vault based authentication.
