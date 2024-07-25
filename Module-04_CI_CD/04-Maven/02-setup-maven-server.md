# Setup Maven Server

## Step-01: Provision an Amazon EC2 instance (or any other VM/PM)

## Step-02: Prerequisites for setting-up Maven

- Connect to your maven server

  ```
  sudo su -
  ```

- Install and Configure `Java`

  ```
  yum install -y java-17-amazon-corretto.x86_64

  java --version
  ```

- Setup Java home path

  ```
  whereis java

  find /usr/lib/jvm/java* | head -n 3
  [/usr/lib/jvm/java-17-amazon-corretto.x86_64]

  vi ~/.bash_profile

  # Create a new variable JAVA_HOME
  JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto.x86_64

  # Add JAVA_HOME to the existing path
  PATH=$PATH:$HOME/bin:$JAVA_HOME
  ```

- To verify the java path

  ```
  echo $PATH

  source ~/.bash_profile
  ```

- Install git

  ```
  yum install -y git
  ```

## Step-03: Setup Maven

- Download the Maven on Maven server. Ref this link: https://maven.apache.org/download.cgi

  ```
  # Move to /opt directory
  cd /opt

  # Download the maven binary
  wget https://dlcdn.apache.org/maven/maven-3/3.9.8/binaries/apache-maven-3.9.8-bin.tar.gz

  # Unzip the downloaded maven tarball
  tar -xvzf apache-maven-3.9.8-bin.tar.gz

  # List all the file to see the unzipped maven directory
  [apache-maven-3.9.8]

  # Get inside the maven home directory
  cd apache-maven-3.9.8
  ```

- Setup home-path for Maven

  ```
  # Update the bash profile with maven path
  vi ~/.bash_profile

  # Create M2_HOME and M2 variable with maven location specs
  M2_HOME=/opt/apache-maven-3.9.8
  M2=/opt/apache-maven-3.9.8/bin

  # Update the PATH variable | Add Maven path
  PATH=$PATH:$HOME/bin:$JAVA_HOME:$M2_HOME:$M2

  [Save the file and exit]

  source ~/.bash_profile
  ```

- Check the maven version
  ```
  mvn --version
  ```
