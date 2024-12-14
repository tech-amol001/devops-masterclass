# Ansible Modules

- <b>_Ansible Modules_</b> are discrete units of code that can be used from the command line or in a playbook task.
- Ansible executes each module, usually on the remote managed node, and collects return values.

## 01. Getting the list of all modules

```
ansible-doc -l

ansible-doc -l | grep <module_name>

# Get documentation for a particular module
ansible-doc <module_name>
```

## 02. Ansible Modules

### 2.1 `debug` module

- The `debug` module prints statements during playbook execution.
- Useful for debugging variables or expressions without necessarily halting the playbook.

```
ansible localhost -a "date"

ansible localhost -m command -a "uptime"

# Execute ansible adhoc command
ansible localhost -m debug -a "msg='Sample text'"

# Verbose mode
ansible localhost -m debug -a "msg='Sample text'" -v
```

## Package Management modules - `yum, apt, pip`

### `yum` module

### `apt` module

```
- name: "Install Nginx version {{ nginx_version }} with apt module"
   ansible.builtin.apt:
     name: "nginx={{ nginx_version }}"
     state: present
```

### `pip` module

## Service Management modules - `service`

###

## `copy` module

## `command` module

## `shell` module

## `lineinfile` & `blockinfile` modules

## File Management modules

## User Management modules

## `cron` module

## Managing `Git (VCS)`
