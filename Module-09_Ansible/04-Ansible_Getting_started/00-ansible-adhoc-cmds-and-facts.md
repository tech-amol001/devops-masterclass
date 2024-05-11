# Introduction to ad hoc commands

- An Ansible ad hoc command uses the **/usr/bin/ansible** command-line tool to automate a single task on one or more managed nodes.
- ad hoc commands are quick and easy, but they are not reusable.

- For more details, refer to https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html

# Ansible Facts

- Ansible facts are data related to your remote systems, including operating systems, IP addresses, attached filesystems, and more.
- You can access this data in the ansible_facts variable.
- By default, you can also access some Ansible facts as top-level variables with the ansible\_ prefix.
- You can disable this behavior using the _INJECT_FACTS_AS_VARS_ setting.

```
- name: Print all available facts
  ansible.builtin.debug:
    var: ansible_facts
```

- To see the all the gathered information, run this command at the command line:

```
ansible <hostname> -m ansible.builtin.setup
```
