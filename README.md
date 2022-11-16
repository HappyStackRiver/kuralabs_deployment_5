<img src="https://github.com/kura-labs-org/kuralabs_deployment_1/blob/main/Kuralogo.png">
<h1 align="center">kuralabs_deployment_5<h1> 
  
Demonstrate your ability to deploy a containerized application.

# Deployment 5
## New Purpose
This deployment was to practice the process of deploying a flask app onto a cluster using Elastic Container Service
## The Steps
1. Prerequisites
  - If an EC2 is not set up already, you would need to set up the Jenkins service
  - An EC2 with default-jre and Docker needs to be spun up, as well as an EC2 with default-jre and Terraform needs to be spun up
  - Default-jre is for the agents to be able to do their job within the assigned servers within our jenkins file 
  - The Docker EC2 instance had my docker hub credentials saved within the machine, which would be used for later on creating the jenkins file
2. Create the infrastructure as Code
  - The terraform main.tf file used ECS to create our cluster and manage our infrastructure
3. Create and configure 2 jenkins agents
  - There was a need to create 2 jenkins agents to be deployed onto 
4. Link GitHub to Jenkins
  - Fork the repo with the Flask App
  - Create access token for Jenkins by using GitHub client
    - admin:repo_hook
5. Jenkins Pipeline creation
  - Create a new item which is a multibranch and/or freestyle project pipeline
  - Add github as a source for the pipeline
  - Validate the source for the pipeline
6. Create the Jenkins file 
  ###  Build and Test Stages
    - The jenkins file would have the steps to build the application within the Jenkins EC2, and test the application, Build and Test Stage
  ### Image Build and Push
    - The jenkins file would then build an image on the docker ec2 instance using a dockerfile within the Docker EC2, then push it onto docker hub for use on a different ec2
  ### Terraform Steps
    - Using the Terraform EC2 and initialize, plan, and apply the infrastructure using ECS
## Tips for Future Me
This deployment has a few moving parts, involving 3 different EC2s to each host a different tool for the deployment. The jenkins file was fun to make, as it was good practice. The deployment did not need to have that many EC2s to host the services we needed. The only reason we did the deployment this way, was to ensure we were not charged for the processing power potentially necessary to run all of the necessary tools. 
 
## Deployment Document Link:
- Link to instructions: https://github.com/kura-labs-org/kuralabs_deployment_5/blob/main/Deployment-5_Assignment.pdf
