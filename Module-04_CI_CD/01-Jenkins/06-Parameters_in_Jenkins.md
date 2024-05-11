# Using Parameters in Jenkins

## What are Parameters in Jenkins?

- You can define the build parameters when you configure either _Freestyle_ or _Pipeline_ projects.
- When you use the build parameters, Jenkins prompts you to enter a value for the defined parameter when you run the Jenkins job.
- Each parameter has a **name** and **value**.
- Some of the commonly used types of parameters are as follows:
  - Boolean
  - Choice
  - Credentials
  - File
  - String
  - Multi-line String
  - Password

## How to define Jenkins Parameters?

- Under **General** setting of your Jenkins job, enable setting "**This project is parameterized**"
- Click **Add Parameter** button >> Select **String Parameter**
  - Name: FIRST_NAME
  - Default Value: BINDESH
  - Description: <some_description_about_parameter>
- In case you want to add more parameter, again click on **Add Parameter** button and follow the above process again.

## How to access Jenkins parameters?

- After you add the parameter, the name that you provided for the parameter must be entered for the corresponding fields in the build/test step in the following format:

```
# Syntax
${name_of_the_parameter}

# Example: Accessing defined parameter
$PROJECT_NAME
```

## Lab-01: Demonstrating the use of paramters in Jenkins jobs

```
# Create a script file
#!/bin/bash
Name=$1
Like=$2
echo "Hello there, I am $Name, and I like $Like"

# Define two parameters for accepting values for 'Name' and 'Like' values

# Build stage
/tmp/sample_script.sh $Name $Like

# Navigate to Build with Paramters section | Pass param values

```
