# ckan
Infrastructure &amp; Automation tooling for deploying ckan.

To run this playbook

```bash
ansible-playbook -K -i inventory.yml ckan.yml
```

## Project Status

Production ready: ❌

Currently this role is not production ready. It will provide a basic single-node ckan installation and nothing else.

## Future Features

This project is not intended to only be a ckan role. In the future Azure Virtual Machine support, remote postgres, Ceph,  and other high availability features are planned to be added.

## Basic Administration
**Creating a Sysadmin user**
```bash
sudo -u www-data /usr/lib/ckan/default/bin/ckan -c /etc/ckan/default/ckan.ini sysadmin add glenn name=glenn
```

## Contributing

This project uses Vagrant as the primary method to test this Ansible playbook.

Set the virtualization provider.
```bash
export VAGRANT_DEFAULT_PROVIDER=libvirt
```
Set the default network interface to use for the bridge.
```ruby
# Vagrantfile
DEFAULT_NETWORK_INTERFACE = "eth1"
```
Start the virtual machine.
```bash
vagrant up
```

