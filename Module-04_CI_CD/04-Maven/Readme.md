# Demystifying Maven

In this section, we will learn below topics:

- What is Maven?
- Why Maven?
- Install and Configure Maven
- Maven Projects
- POM.xml
- Build maven project
- Execute maven project

## 01. What is a Build?

- A software build is a set of executable code that is ready for use by customers.
- The DevOps team compiles the source code, such as code in Java or C++, into binaries to make sure it's functional and test code quality before committing it.

## 02. Understanding Build process

The process followed by a software development team when building software is as listed below:

- Find the source code from an **Open Source repository** such as _GitHub_.
- Use a **build tool** like Ant, **Maven** or **Gradle** to compile the code.
- **Debug** the code and check for **dependencies**.
- Run different versions of the build and conduct unit tests.
- Link the relevant files and send notifications to the stakeholders.

## 03. What is Apache Maven?

- **Apache Maven** is a build tool, which helps developer in building application.
- The Apache Maven is a Java build tool which can be used compile, test and package enterprise softwares.
- Maven provides many compelling features beyond the ability to package and compile code, such as the following:
  - Solves the dependency management problem.
  - Downloads third-party JAR files that some apps require.
  - Provides an extensive, third-party plugin architecture.
  - Enables switching between development profiles.
  - Integrates with DevOps tools such as Jenkins and Docker.

## 04. [Maven Installation](https://maven.apache.org/download.cgi)

### Step-4.1: Maven installation on Amazon Linux 2 AMI

```
# Download maven repo details
sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo

sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo

sudo yum install -y apache-maven
```

### Setup Maven on other Linux distros

- Provision an EC2 Instance and connect to it over SSH
- Install Java on the VM/PM

```
# Find java program

# Set Java Home path


```

- Download and Install Maven from this link: https://maven.apache.org/download.cgi

```
cd /opt
sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz

# Extract the compressed download
sudo tar -xvzf apache-maven-3.9.6-bin.tar.gz

# Get inside the extracted directory
cd apache-maven-3.9.6
```

- Set Maven path

```
# Set Maven Path
sudo vi ~/.bash_profile

M2_HOME=/opt/apache-maven-3.9.6
M2=/opt/apache-maven-3.9.6/bin

# Append the above two variables into existing PATH
PATH=<YOUR_EXISTING_PATHS>:$M2:$M2_HOME

# Save the file and Quit

# Bring the updated path live
source ~/.bash_profile

# Check Maven version
mvn -version
```

## 05. What are `Apache Maven phases`?

- To perform various build operations, Apache Maven provides a variety of phases that admins can invoke on a project through the `mvn` command.
- Commonly used Apache Maven phases include:
  - **clean** – deletes the target folder.
  - **compile** – turns source files into class files.
  - **test** – runs a project’s unit tests.
  - **package** – creates an artifact such as a JAR, ZIP or WAR file.
  - **install** – moves a created artifact into a Maven repository.

## 06. How does `Maven` manage Java dependencies?

- At the root of every Maven project is a Project Object Model file named **pom.xml**. This file lists all of a project's dependencies on third-party libraries or external JAR files.
- You can also create complex dependencies if you set up one pom.xml file as parent to another **pom.xml file**.
- This is often done with frameworks including Spring Boot to reference a large number of projects.

## 07. What is the difference between `Maven` and `Jenkins`?

- **Apache Maven** and Jenkins are not similar technologies, as many people mistakenly think.
- Jenkins is a continuous integration (CI) tool that automates pulling code from source code repositories (GitHub, GitLab, etc.) and subsequently compiling it.
- **Jenkins** automates the task of integrating code — but to compile code, Jenkins requires a build tool.
- While Jenkins integrates with many alternate build tools such as Gradle and Ivy, Jen*kins offers out-of-the-box Maven support*.
