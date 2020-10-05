## Application Requirements

* Timeoff-management fork on local repository.
* Application must be deployed using a fully automated continuous integration solution based on Jenkins, triggered by a change in source control.
* Artifact management to be done through an artifact repository management solution.
* Required infrastructure running on virtualization solution or preference, provisioned using some sort of infrastructure as code through configuration management. 

## Software Architecture

![diagram](https://github.com/gmoraa/timeoff/blob/main/diagram.png)

## Usage

ansible-playbook -i ./inventory main .yml
