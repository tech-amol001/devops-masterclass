# Introducing AWS SDK (Boto3)

## What is Boto3?

- Boto3 is the Amazon Web Services (AWS) SDK for Python.
- It enables Python developers to create, configure, and manage AWS services, such as EC2 and S3. Boto3 provides an easy-to-use, object-oriented API, as well as low-level access to AWS services.
- Boto3 is built on the top of a library called Botocore, which the AWS CLI shares.
- Botocore provides the low-level clients, session and credentials, and configuration data. Boto3 built on the top of Botocore by providing its own session, resources, collections, waiters, and paginators.

## Working with Boto3

### Step-01: Installing Boto3 & AWS CLI

```
# Windows users
pip install boto3

# Linux users
pip3 install boto3 --user

# Install AWS CLI
sudo pip install awscli

```
