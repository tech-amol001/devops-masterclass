# Ansible Playbooks

## 01. Playbook `Syntax`

- Ansible playbooks are YAML files.
- In order to write an ansible playbook, you must be familiar with YAML.
- A **playbook** is composed of one or more **plays** in an ordered list.
- The terms _playbook_ and _play_ are sports analogies.
- Each play executes part of the overall goal of the playbook, running one or more tasks.
- Each task calls an Ansible module.

<img src="https://github.com/kbindesh/devops-masterclass/blob/main/Module-09_Ansible/07_Ansible_Playbooks/images/playbooksyntax.png" width="500" height="450">

- Your playbook can include more than just a hosts line and tasks.
- You can add other [Playbook Keywords](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html#playbook-keywords) at the playbook, play, or task level to influence how Ansible behaves.

## 02. Playbook Execution

- A playbook runs the tasks in order from top to bottom.
- Playbooks with multiple _plays_ can orchestrate multi-machine deployments, running one play on your webservers, then another play on your database servers, then a third play on your network infrastructure, and so on.
- At a minimum, each play defines two things:
  - the managed nodes to target, using a pattern
  - at least one task to execute

### Task execution

- By default, Ansible executes each task in order, one at a time, against all machines matched by the host pattern.
- Each task executes a module with specific arguments.
- When a task has executed on all target machines, Ansible moves on to the next task.
- You can use [strategies](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_strategies.html#playbooks-strategies) to change this default behavior.
- Within each play, Ansible applies the same task directives to all hosts.
- If a task fails on a host, Ansible takes that host out of the rotation for the rest of the playbook.

### Desired state and `idempotency`

- Most Ansible modules check whether the desired final state has already been achieved, and exit without performing any actions if that state has been achieved, so that repeating the task does not change the final state.
- Modules that behave this way are often called **idempotent**.
- Whether you run a playbook once, or multiple times, the outcome should be the same.
- However, not all playbooks and not all modules behave this way.

### Running playbooks

```
ansible-playbook <playbook_name>.yml
```

### Running playbooks in check mode (dryrun)

- To run a playbook in check mode, you can pass the **-C** or **--check** flag to the ansible-playbook command:

```
ansible-playbook --check playbook.yaml
```

## 03. Verifying playbooks

- You may want to verify your playbooks to catch syntax errors and other problems before you run them.
- The ansible-playbook command offers several options for verification, including:
  - **--check**
  - **--diff**
  - **--list-hosts**
  - **--list-tasks**
  - **--syntax-check**
- The Tools for validating playbooks describes other tools for validating and testing playbooks.

### ansible-lint

- You can use **ansible-lint** for detailed, Ansible-specific feedback on your playbooks before you execute them.

```
$ ansible-lint verify-playbook.yml
```

## 04. Listing Tasks in a Playbook

```
ansible-playbook --list-tasks bindesh-playbook.yml
```
