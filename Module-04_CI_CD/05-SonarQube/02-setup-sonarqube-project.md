# Create and Configure SonarQube Project

## Step-01: Create a SonarQube project

- Sign-in to SonarQube portal

- On the landing page, select **Manually** tile for question "How do you want to create your project?"

  - **Project Key**: maven-project
  - **Display Name**: maven-project
  - **Branch Name**: main (default)
  - Click on **Set up** button

- **How do you want to analyze your repository?**: Locally
- **Generate a project token**: Provide a label and click on **Generate** button

  ```
  # Sample Sonarqube project token
  test-project: sqp_b988eeff0ff1f3448016f80acf53d87d304dc297

  ```

- **Run analysis on your project**: Maven

  ```
  # Copy the following auto-generated command | We will need these details on Step#2

  mvn clean verify sonar:sonar \
  -Dsonar.projectKey=test-project \
  -Dsonar.host.url=http://120.29.41.45:9000 \
  -Dsonar.login=sqp_b988eeff0ff1f3448016f80acf53d87d304dc297
  ```

Step-02: Perform code review (manually) on Maven server

- Connect to your Maven server

- Clone the Maven project from remote git repo.

  ```
  git clone https://github.com/kbindesh/maven-sample-repo.git
  ```

- Review the code using Sonarqube scanner

  ```
  # Execute the command that we copied on Step#1
  mvn clean verify sonar:sonar \
  -Dsonar.projectKey=test-project \
  -Dsonar.host.url=http://120.29.41.45:9000 \
  -Dsonar.login=sqp_b988eeff0ff1f3448016f80acf53d87d304dc297
  ```

- Check the quality gate in the execution logs.

Step-03: Verify the code scanned results

- Hop over to SonarQube server >> Select your Project

- You should see the scanned results with code smells, recommendations etc.
