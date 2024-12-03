# Setting-up environment for `Ansible`

In this lab, there will be two machines:

- **Ansible Server (Controller node)** - where we will execute all the playbooks.

  - I've used Amazon Linux 2 ec2 instance for the Ansible controller.

- **Target Machine (client/managed node)** - to which "_Ansible Server_" will send the instructions mentioned via playbook tasks and eventually will be executed here.

  - I've used RHEL8 ec2 instance here.
  - You may use any other linux/windows machine.

- :warning: Make sure there is a connectivity between both the machines over SSH/RDP.

- Provision both the machines in the same Amazon VPC.

## Step-01: Setup `Ansible controller` on Amazon Linux 2 EC2 instance

### 1.1: Provision an EC2 instance

- AMI: Amazon Linux 2 (5.10 Kernel)
- Instance Type: t2.micro
- Key Pair: Create a new key pair
- VPC & Subnet: Default
- Security group: Allow SSH(22) ingress | Outbound allow all
- Storage: 10 GB (root volume)

### 1.2: Preparing Ansible server for installing Ansible

```
sudo su -

useradd ansibleadmin

passwd ans-ansibleadmin

hostname ansible-controller

vi /etc/hostname

[Update the hostname and restart the machine]

# Add ansibleadmin user to the sudoers file
visudo

# Add ansibleadmin after root user
ans-admin   ALL=(ALL)   NOPASSWORD: ALL

# Switch to ansibleadmin user to generate the ssh keys
sudo su - ansibleadmin

ssh-keygen

ls .ssh/
[You should see generated ssh keys]

exit

sudo vi/etc/sshd/sshd_config

PasswordAuthentication yes

[Save the file and exit]

server sshd restart
```

### 1.3: Install and configure Ansible

- Connect to the EC2 instance that you created in Step#1.
- Now, execute following commands:

```
# Install epel-release packages in AnsibleServer
$ sudo amazon-linux-extras install -y epel

# Disable ansible2 package from amazon-linux-extras repo
$ sudo amazon-linux-extras disable ansible2

# Enable epel repo from yum-config-manager
$ sudo yum-config-manager --enable epel

# Install Ansible from epel repo
$ sudo yum --enablerepo epel install -y ansible

# Check ansible version
$ ansible --version
```

## Step-02: Setup `Ansible Managed node` (client) on RHEL EC2 instance

### 2.1: Provision an EC2 instance

### 2.2: (Optional) Update the hostname

```
sudo su -

hostname rhel-client-01

vi /etc/hostname

[update the hostname to 'rhel-client-01']
```

### 2.3: Create a new user (ansible-ops) for IT Ops using Ansible controller

```
useradd ansible-ops

passwd ansible-ops
```

### 2.4: Enable Password-based Authentication

```
vi /etc/ssh/sshd_config

PasswordAuthentication yes
```

### 2.5: Add `ansible-ops` user to the `sudoers` file

```
visudo

# Add just after the ec2-user settings
ansible-ops   ALL=(ALL)   NOPASSWD: ALL

service sshd reload
```

## Step-03: Copy generated SSH key to managed node (RHEL client)

- Switch to `ansible controller` node and run following commands:

```
sudu su - ansibleadmin

ssh-copy-id <private_ip_of_rhel_client_vm>

[If prompted, enter the password for ansibleadmin]

[Now, you should be able to ssh to rhel managed node using ssh key without password]
ssh <private_ip_of_rhel_client_vm>

exit
```
