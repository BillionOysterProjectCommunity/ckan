# ckan
Infrastructure and Automation tooling for deploying ckan.

To run this playbook

```bash
ansible-playbook -K -i inventory.yml ckan.yml
```

## Project Status

Production ready: ❌

Currently this role is not production ready. It will provide a basic single-node ckan installation and nothing else.

## Future Features

This project is not intended to only be a ckan role. In the future AWS EC2 support, remote postgres (RDS), Ceph,  and other high availability features are planned to be added.

## Basic Administration
**Creating a Sysadmin user**
```bash
sudo -u www-data /usr/lib/ckan/default/bin/ckan -c /etc/ckan/default/ckan.ini sysadmin add admin name=admin
```
**Xloader configuration**
1. Login as an admin user
1. Go to API Tokens
1. Create an API token for xloader
1. Insert the API token into `/etc/ckan/default/ckan.ini`
```ini
ckanext.xloader.api_token = API_TOKEN
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

