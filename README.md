# WordPress server setup

=========

This project is designed for setup of a fully functional WordPress installation on a Ubuntu server.

## Requirements

------------

This project is designed to work with Ubuntu distributions. It requires the following:

- Ansible 2.10.8 or higher
- `sshpass` for running the playbook with SSH password authentication.

## Variables

------------

The following variables should be configured:

- **`user.name`**: The name of the sudo user to be created.
- **`user.sudo_password`**: The password for the sudo user.
- **`user.public_key`**: Path to the SSH public key to be added to the sudo user's `~/.ssh/authorized_keys`.
- **`journalctl_max_disk_usage`**: Max disk space that could be used by journal.
- **`mysql_root_password`**: Root user passport for MySQL server.
- **`php.version`**: The version of PHP we want installed.
- **`hosts`**: The target host for the playbook. This variable defines the host to be configured and should match the corresponding entry in the Ansible inventory file. For example, you can pass `hosts=local_vm` to apply the playbook to the `local_vm` host.

## Dependencies

------------

This project depends on several roles

## License

------------

MIT License

## Testing Guide

------------

To run a local test for this role, use the following commands:

```bash
# To install roles locally
ansible-galaxy install -r ansible_requirements.yml --roles-path roles
# To run playbook
ansible-playbook -i tests/local_inventory.ini wordpress-server-setup.yml -u root -k --ask-vault-pass --extra-vars "hosts=local_vm"
```

## Author Information

------------

This project was created by Stefan, aka enabler, aka r0gu3cic. For any inquiries or further information, please reach out via [GitHub](https://github.com/r0gu3cic).
