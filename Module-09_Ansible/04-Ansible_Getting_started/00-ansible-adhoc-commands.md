# Introduction to ad hoc commands

- An Ansible ad hoc command uses the **/usr/bin/ansible** command-line tool to automate a single task on one or more managed nodes.
- ad hoc commands are quick and easy, but they are not reusable.

- For more details, refer to https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html

### Configuring ansible for running modules on `Localhost`

```
# Update the /etc/ansible/hosts file to add localhost
localhost ansible_connection=local

# Now, tell ansible the location of host file through /etc/ansible/ansible.cfg
inventory      = /etc/ansible/hosts
```

### Display message on the standard output

```
# Execute ansible adhoc command
ansible localhost -m debug -a "msg='Sample text'"

# Verbose mode
ansible localhost -m debug -a "msg='Sample text'" -v
```

### Working with the Packages

```
ansible localhost -b -m yum -a "name='git' state='installed'"

ansible localhost -b -m yum -a "name='httpd' state='installed'"

ansible localhost -b -m service -a "name='httpd' state='started'"

ansible localhost -b -m service -a "name='httpd' enabled='yes'"
```

### Manage Files and Directories

```
# Get info about a file
ansible localhost -m stat -a "path='/etc/ansible/hosts'" -v

# Copy a file to the servers
ansible servers -m copy -a "src=/etc/hosts dest=/tmp/hosts"

# Retreive a file from the servers
ansible servers -b -m fetch -a "src=/etc/hosts dest=/tmp"

# Create a Directory
ansible servers -m file -a "dest=/tmp/test mode=644 state=directory"

# Create a File
ansible localhost -m file -a "dest=/tmp/test.txt mode=644 state=touch"

# Delete directories and files
ansible localhost -m file -a "dest=/tmp/test.txt state=absent"
```

### Managing Git (VCS)

```
ansible app -b -m git -a "repo=git://example.com/path/to/repo.git dest=/opt/myapp update=yes version=1.2.4"
```
