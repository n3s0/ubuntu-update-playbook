# Ubuntu Server Update Playbook
---

## Summary
---

The objective of this playbook is to have the capability to update multiple
instances of Ubuntu Server at a time. You just add the server to your inventory
file and off you go.

I've been meaning to automate tasks in multiple ways for various servers for a
long time. So, I thought this would be the best starting point for this.

!---CAUTION---!

One thing I wouldn't recommend doing is running this Ansible playbook on servers
that need to be updated in a specific order. As I learn more about Ansible
playbooks, I will try to figure out a way to prioritize or create a dependancy
for updating servers in a certain order. I'm thinking about this mostly for
those that have database replicas that need to be rebooted at the same time.

For now. Updates will be performed in order or all at once as listed in the
inventory file.
