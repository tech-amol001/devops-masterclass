# Configure Jenkins server for Master-Slave setup

## Step-01: Setup `Jenkins Master system`

## Step-02: Setup `Jenkins Slave system`

## Step-03: Upload the slave node credentials on Jenkins Master node

- **Manage Jenkins** >> **Manage Credentials** >> **System** >> **Global credentials** >> **Add credentials**

- **kind**: ssh username with private key

- **Scope**: Global

- **ID**: maven_slave

- **Username**: ec2-user

- **private key**: <YOUR_KEY>.pem key content

## Step-04: Onboard Jenkins slave node

Follow the below setups to add previously created slave node to the Jenkins master:

- Navigate to **Manage Jenkins** >> **Manage nodes and clouds** >> **New node** >> **Permanent Agent**

- **Number of executors**: 3

- **Remote root directory**: /home/ec2-user/jenkins

- **Labels**: maven

- **Usage**: Use this node as much as possible

- **Launch method**: Launch agents via SSH

- **Host**: <PRIVATE_IP_OF_THE_SLAVE_NODE>

- **Credentials**: <JENKINS_SLAVE_CREDENTIALS>

- **Host Key Verification Strategy**: Non verifying Verification Strategy

- **Availability**: Keep this agent online as much as possible

## Step-05: Create a test Jenkins job to be executed on Slave node
