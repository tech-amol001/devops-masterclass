# Configure Maven Plugins and Dependencies

## Step-01: Check the pom.xml elements

- Check the pom.xml schema version

- Check the default packaging format

- Check the default compiler source version (java version)

- Check the dependencies

- Check the build section for plugins

## Step-02: Update the pom.xml

- Get inside the maven project directory and build the app

  ```
  cd bin-demo-project

  # Install the package into the local repository
  mvn clean install

  [This time it will take less time than previous runs]
  [Make a note - there is no test class]
  ```

- Now, update the pom.xml file

  ```
  vi pom.xml
  ```

- Delete the entire dependencies block and build the app again

  ```
  mvn clean install

  [Because there are no test cases, no unit testing will be performed]
  ```
