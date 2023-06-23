#EC2 Instance Creation and Configuration with-CircleCI-and-Ansible
This project provides a template and configuration files for creating and configuring EC2 instances using Ansible and CircleCI. The goal is to automate the provisioning and setup of EC2 instances for your repository.

#Prerequisites
Before getting started, make sure you have the following prerequisites installed:

Ansible: [Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
CircleCI CLI: [Installation Guide](https://circleci.com/docs/local-cli/#installation)
AWS CLI: [Installation Guide](https://aws.amazon.com/cli/)
# Project Structure
The project contains the following files and folders:

- template.yml: The CloudFormation template file used for provisioning EC2 instances.
- circleci folder: Contains CircleCI configuration files for continuous integration.
- ansible folder: Contains Ansible roles and playbook for configuring the EC2 instances.
- inventory: Inventory file listing the target EC2 instances.

#Getting Started
To use this project, follow these steps:

1. Clone the repository to your local machine.
2.  Customize the template.yml file to suit your EC2 instance requirements.
3.  Update the inventory file with the appropriate IP addresses or DNS names of your EC2 instances.
4. Modify the Ansible roles in the ansible folder to configure your instances as needed.
5. Update the CircleCI configuration files in the circleci folder to match your repository's structure and requirements.

#Provisioning EC2 Instances
To provision EC2 instances using the CloudFormation template:

1. Open the AWS Management Console.
2. Create an AWS IAM user with necessary permissions for CloudFormation, EC2, and related services.
3. Set up AWS CLI by configuring the IAM user credentials on your local machine.
4. Update the .circleci/config.yml file in the circleci folder:
5. Replace <AWS_ACCESS_KEY_ID> and <AWS_SECRET_ACCESS_KEY> placeholders with your IAM user's credentials.
6. Modify the AWS region and stack name if desired.
7. Commit and push the changes to your repository.<br>
CircleCI will automatically trigger the job defined in .circleci/config.yml, which will use the AWS CLI to create the CloudFormation stack and provision the EC2 instances based on the template.yml file.

# Configuring EC2 Instances with Ansible
To configure the EC2 instances using Ansible:

1. Ensure you have Ansible installed on your local machine.
2. Navigate to the ansible folder in the project.
3. Modify the roles and playbook according to your desired configuration.
4. Update the inventory file with the appropriate EC2 instance details.
5. Run the Ansible playbook using the following command:
ansible-playbook -i inventory playbook.yml

# Continuous Integration with CircleCI
This project includes configuration files for CircleCI, allowing for continuous integration of your repository, including infrastructure provisioning.

To set up CircleCI for your repository:

1. Sign up for a CircleCI account and connect your repository.
2. Customize the .circleci/config.yml file according to your repository's needs.
3. Commit and push the changes to your repository.
CircleCI will automatically trigger builds and execute the defined workflows based on the changes pushed to your repository.
