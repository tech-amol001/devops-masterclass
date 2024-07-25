# Create a Maven WebApp Archetype

- `maven-archetype-webapp` is an archetype which generates a sample Maven webapp project:

  ```
  project
  |-- pom.xml
  `-- src
      `-- main
          `-- webapp
              |-- WEB-INF
              |   `-- web.xml
              `-- index.jsp
  ```

- To generate a new project from this archetype, run:

  ```
  mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-webapp -DarchetypeVersion=1.4
  ```

- OR you create a new webapp archetype project manually, as follows:

  ```
  mvn archetype:generate

  groupId/ArtifactId: 1757

  archetypeVersion = 1.4

  groupId = com.democompany

  artifactId = bin-demo-project

  version = default

  package name = default

  [Confirm by entering 'y']
  ```

- You will see a new directory created inside present directory:

  ```
  ls -la

  [you will see a new directory with a label of artifactId, here is bin-demo-project]
  ```
