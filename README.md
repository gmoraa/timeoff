## Application Requirements

* Timeoff-management fork on local repository.
* Application must be deployed using a fully automated continuous integration solution based on Jenkins, triggered by a change in source control.
* Artifact management to be done through an artifact repository management solution.
* Required infrastructure running on virtualization solution or preference, provisioned using some sort of infrastructure as code through configuration management. 

## Version 1.0.0

## Usage

ansible-playbook -i ./inventory main .yml

## Software Architecture

Given the requirements listed above I created all the components as code, that means ansible execution will create 3 Docker containers and 1 virtual machine running Ubuntu. 

Behind this logic there is a reason, connecting a local environment to a cloud environment could generate too much chaos. Think about connecting Github in the cloud to a local Jenkins for Continuos Integration or a Jenkins in the Cloud to a local virtual machine for the Continuous Deployment, it's for that reason this architecture involves all 4 applications locally.

![diagram](https://github.com/gmoraa/timeoff/blob/main/diagram.png)

## To improve

The connectivity(webhook) between GitLab and Jenkins is missing as code aswell as the Groovy file for Jenkins to detect the changes in the code.
