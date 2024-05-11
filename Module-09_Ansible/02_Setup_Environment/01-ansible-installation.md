# Setting up the environment for Ansible

There will be two machines in this setup:

1. **Ansible Server (Control node)**, where we will execute all the playbooks. We are using CentOS 7.x machine in this lab.

2. **Target Machine (client node)**, to which "_Ansible Server_" will send the instructions mentioned via playbook tasks and eventually will be executed here. It can be any linux machine.

3. :warning: Make sure there is a connectivity between both the machines over SSH/RDP

<img src="https://github.com/novatecstack/ansible-masterclass/assets/121426292/89409280-97b1-4c22-b2da-e6fe43c52417" data-canonical-src="https://github.com/novatecstack/ansible-masterclass/assets/121426292/89409280-97b1-4c22-b2da-e6fe43c52417" width="600" height="180" />

## 01. Setup Ansible Server on `Amazon Linux 2 (EC2 Instance)`

### Step-01: Provision an EC2 instance with below specifications:

- AMI: Amazon Linux 2 (5.10 Kernel)
- Instance Type: t2.micro
- Key Pair: Create a new key pair
- VPC & Subnet: Default
- Security group: Allow SSH(22) ingress | Outbound allow all
- Storage: 10 GB (root volume)

### Step-02: Install and configure Ansible

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

## 02. Setup Ansible on `RHEL 8`

- There are multiple ways by which you can install **ansible**:

  - **Using default package manager such as yum, dnf, apt etc**

  - **Using pip**

  - **Using source compile file**

### Step-01: Install using package manager on RHEL 8

- First register your system to RedHat Subscription manager

```
$ subscription-manager register
```

- Attach your Red Hat Ansible Engine subscription in order to find the Red Hat Ansible Engine subscription

```
subscription-manager list --available

subscription-manager attach --pool=<pool id>
```

- Enable the Red Hat Ansible Engine Repository

```
subscription-manager repos --enable ansible-VERSION-for-rhel-8-x86_64-rpms

# Example: To subscribe to ansible 2.9 repository
subscription-manager repos --enable ansible-2.9-for-rhel-8-x86_64-rpms
```

- Install Ansible Engine using default package manager

```
dnf -y install ansible
```

## 03. Setup Ansible on `CentOS 8`

### Step-01: Install epel repository

```
dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm -y

# List repos for epel
dnf repolist
```

### Step-02: Install ansible

```
# Search for the ansible package in the available repository
dnf search ansible

# Install ansible using the default package manager
dnf install -y ansible

# Check the version of ansible
ansible --version
```
