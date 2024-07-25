# Install and Configure SonarQube on Linux VM (Amazon Linux)

## Step-01: Provision an EC2 instance (VM)

- **Instance Type**: t2.small (min 2GB memory)
- **AMI**: Amazon Linux 2
- **Security Group**:

  - **Ingress**
    - Allow 22 (SSH)
    - Allow 9000 (sonarqube)
  - **Egress**: Allow all traffic from the web (default)

- Connect to your sonarQube server using any SSH client (mobaxterm/putty/ssh)

## Step-02: Prerequisites

- Switch to root user:

  ```
  sudo su -
  ```

- The only prerequisite for running SonarQube is to have a **Java** installed on your machine.

  ```
  # Check if the java is already installed
  java --version

  [If not installed, process with the following commands or skip rest of the commands]

  yum install -y java-17-amazon-corretto.x86_64
  ```

- **Minimum hardware requirement**: 2GB RAM + 1 GB of free RAM for operating system

## Step-03: Download and Setup SonarQube

- Download the sonarqube community edition from here: </br>
  https://www.sonarsource.com/products/sonarqube/downloads/

  ```
  cd /opt
  wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.6.92038.zip
  ```

- Extract the package

  ```
  unzip sonarqube-9.9.6.92038.zip

  ls -l sonarqube-9.9.6.92038
  ```

- (Optional) In case you want to override the default sonarqube properties, update the sonar.properties file

  ```
  cd sonarqube-9.9.6.92038/conf

  ls -l

  [You should see the sonar.properties file]
  ```

- Create a new user for SonarQube operations

  ```
  useradd sonaradmin
  ```

- Change the ownership of SonarQube and start the service

  ```
  cd /opt/sonarqube-9.9.6.92038

  chown -R sonaradmin:sonaradmin /opt/sonarqube-9.9.6.92038

  # List the files to verify the owner update
  ls -l
  ```

- Switch to `sonaradmin` user to start the service

  ```
  su - sonaradmin
  ```

- Start the sonarqube service

  ```
  # Move to sonarqube home directory
  cd /opt/sonarqube-9.9.6.92038/bin

  # Start the service
  ./sonar.sh start

  # Check the sonarqube service status
  ./sonar.sh status

  [Service should be in running state]

  # Check the ports on which server is listening
  netstat -tulpn

  [Should see server listening on port 9000]
  ```
