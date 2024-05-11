# Static Code Analysis with `SonarQube`

## What is Code Quality?

- Is the code bug free?
- Is the code secure?
- Do you have a Redundant code?
- Have you tested the code properly?
- Is it a Complex code?
- Unnecessay elements in the code?

## What is Static Code analysis?

- Static Code Analysis is usually performed as part of a Code Review and is carried out at the _implementation phase_ of a software development Lifecycle (SDLC).
- Static Code Analysis commonly refers to the running of static code analysis tools that attempt to highlight possible vulnerabilities within 'static' (non-running) source code by using techniques such as _Taint Analysis_ and _Data Flow Analysis_.

- Static analysis is generally good at finding coding issues such as:

  - Programming errors
  - Coding standard violations
  - Undefined values
  - syntax violations
  - Security vulnerabilities

## How is static analysis of code is done?

- Generally, static analysis occurs before software testing in early development.
- Once the code is written, a static code analyzer should be run to look over the code.
- It will check against defined coding rules from standards or custom predefined rules.
- Once the code is run through the static code analyzer, the analyzer will have identified whether or not the code complies with the set rules.
- Developers can then begin to fix any apparent mistakes, generally starting from the most critical ones.
- Once the code issues are resolved, the code can move on to testing through execution.

## Commonly used Static Code Analysis tools

- **SonarQube**
- SonarCloud
- Coverity
- Veracode
- Codescene

## SonarQube Overview

- SonarQube is a Code Quality Management Tool
  - Code Analysis
  - Test Reports
  - Code Coverage
- For more details about SonarQube, here is the official documentation link: https://docs.sonarsource.com/sonarqube/latest/

## Components of SonarQube

- SonarQube Server
  - Rules - Instructions that you must follow while writing the code
  - Database
  - Web Interface (GUI)
- SonarScanner
  - Source code

## How SonarQube works?

## Setup SonarQube on Amazon EC2 Instance (Amazon Linux 2)

- Provision a new EC2 Instance, say SonarQube server with below specs:
  - Instance Type: t2.micro (recommended is atleast 2GB memory)
  - AMI: Amazon Linux 2
  - VPC & Subnet: Default
  - Security Group: Allow traffic on port 22 and 9000
- Install Java

## SonarQube console walkthrough

## SonarQube Integration with Jenkins
