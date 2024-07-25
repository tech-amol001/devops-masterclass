# Create and Build Java App using Maven (Linux)

## Step-01: Create a new maven project

- You may clone the sample maven project from this github repos: </br>

  ```
  git clone https://github.com/kbindesh/maven-sample-repo.git
  ```

## Step-02: Validate, Compile, Unit Test, Build and Deploy Java App using Maven

- Get inside the cloned maven project directory and demonstrate manven lifecycle goals:

  ```
  # Validate the project
  mvn validate

  # Compile the Project | Pull all the required packages | Create Target dir
  mvn compile

  # Compile the test cases | Inside target folder, test classes folder will be created
  mvn test-compile

  # Perform unit testing of java app
  mvn test

  # Package the java app | By default, it will package the app as a .jar file in target directory
  mvn package

  # Install the package into the local repository | Default local repo location

  find / -name.m2
  [/root/.m2]

  mvn install
  [you will see a new directory created inside the m2 dir with the .jar]
  ```
