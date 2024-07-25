# Demystifying Maven Settins (settings.xml)

## 01. Maven `settings.xml` overview

- The settings element in the settings.xml file contains elements used to define values which configure Maven execution in various ways, like the pom.xml, but should not be bundled to any specific project, or distributed to an audience.
- These include values such as the local repository location, alternate remote repository servers and authentication information.

## 02. settings.xml location

- There are two locations where a settings.xml file may live:

  1. The Maven install

     - `${maven.home}/conf/settings.xml`
     - global settings

  2. A user's install
     - `${user.home}/.m2/settings.xml`
     - user settings

## 03. Access the default settings.xml file

```
cd /opt/apache-maven-3.9.8/conf

ls -l

[You will find a setting.xml file]
```

## 04. References

- https://maven.apache.org/settings.html
