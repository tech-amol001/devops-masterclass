# Ansible Ad-hoc Commands

### Ansible ad-hoc command syntax

```
# Syntax
ansible <host_pattern> -m module <module_name> -a <arguments>

# Example
ansible localhost -m debug -a "msg='Hello there'"
```

### Print a statement - `debug` module

- The `debug` module prints statements during playbook execution.
- Useful for debugging variables or expressions without necessarily halting the playbook.

```
ansible localhost -m debug -a "msg='Hello there'"
```

### Executing linux commands - `command` & `shell` module

- You can use `command` and `shell` modules

```
# Get the free memory details using command module (uses Python)
ansible localhost -m command -a "free -mh"

# Get the free memory details using shell module
ansible localhost -m shell -a "free -mh"

# Get the free memory details+date using shell module
ansible localhost -m shell -a "free -mh;date"
```

### File Management modules - `file, stat, copy, lineinfile, blockinfile, template, fetch`

- **`file` module**
  - To create/delete a file or directory
  - To get the existing file information
  - To modify the file paramters like mode, owner etc.

```
# Create a file on the managed node
ansible all -m file -a "path='/tmp/test.txt' state='touch'"

# Create a file with custom permissions
ansible all -m file -a "path='/tmp/test1.txt' mode='0755' state='touch'"

# To verify the created files, list files using "command" module
ansible all -m command -a "ls -lrt /tmp"

# Change the permission of test1.txt file
ansible all -m file -a "path='/tmp/test1.txt' mode='0777'"

# Delete a file
ansible all -m file -a "path=/path/test1.txt' state='absent'"
```

- **`stat` module**
