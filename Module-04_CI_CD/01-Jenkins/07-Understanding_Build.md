# CI/CD Automation using Jenkins

## Understanding the Build process

<build_activities_and_flow_here>

## Lab: Build Application Manually on Jenkins server

### Step-01: Pull the application source code (java) on your jenkins server manually

- You may clone the sameple java application code from here: https://github.com/kbindesh/java-app-for-mvn on to Jenkins server.

```
sudo git clone https://github.com/kbindesh/java-app-for-mvn.git

```

-

### Step-02: Prepare the jenkins server for initiating the build

- Install Maven

```
# To check if maven already exists on your system
mvn --version

# Install Maven
sudo yum install -y maven

```

### Step-02: Package Application (here it is java app)

### Step-03: Build the Application with jenkins

### Step-04: Capture build artifacts

### Step-05: Configure jobs to capture test results
