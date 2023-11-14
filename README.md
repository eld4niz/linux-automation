# Basic Ansible Configuration

## Ansible Inventory
The inventory is the collection of the machines that we would like to manage. Usually, the default location for inventory is /etc/ansible/hosts but we can also define a custom one in any directory.

## Adding variables to inventory

You can store variable values that relate to a specific host or group in inventory. To start with, you may add variables directly to the hosts and groups in your main inventory file.

We document adding variables in the main inventory file for simplicity. However, storing variables in separate host and group variable files is a more robust approach to describing your system policy.

---

### ansible_user

User that you need to access through ssh

### ansible_password

User password for that specific user

### become

True or False, if you want to do anything as root user you should have this variable as true.


## Working with Dynamic Inventories

If your Ansible inventory fluctuates over time, with hosts spinning up and shutting down in response to business demands, the static inventory solutions described in How to build your inventory will not serve your needs. You may need to track hosts from multiple sources: cloud providers, LDAP, Cobbler, and/or enterprise CMDB systems.

Ansible integrates all of these options through a dynamic external inventory system. Ansible supports two ways to connect with external inventory: Inventory plugins and inventory scripts.

Inventory plugins take advantage of the most recent updates to the Ansible Core code. We recommend plugins over scripts for dynamic inventory. You can write your own plugin to connect to additional dynamic inventory sources.

You can still use inventory scripts if you choose. When we implemented inventory plugins, we ensured backwards compatibility through the script inventory plugin. The examples below illustrate how to use inventory scripts.



## Ansible Vault

Ansible Vault encrypts variables and files so you can protect sensitive content such as passwords or keys rather than leaving it visible as plaintext in playbooks or roles. To use Ansible Vault you need one or more passwords to encrypt and decrypt content. If you store your vault passwords in a third-party tool such as a secret manager, you need a script to access them. Use the passwords with the ansible-vault command-line tool to create and view encrypted variables, create encrypted files, encrypt existing files, or edit, re-key, or decrypt files. You can then place encrypted content under source control and share it more safely.

### Usecase
---

```bash
ansible-vault create vault.yml
```

Then you'll enter your password or key and after saving it will encrypt your password or key. Also you'll enter vault password.

## Conclusion

I'll try to update as I learn more about Ansible and other Linux Automation tools on this repository. Contributions are welcome, and if you have a preferred Linux automation tool, feel free to create a new pull request. The current structure follows the default README.md. If a new tool is added, I will update the repository by organizing each tool's scripts and Markdown files into dedicated directories.
