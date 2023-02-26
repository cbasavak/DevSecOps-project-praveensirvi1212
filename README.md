# DevSecOps-project

In this project, In this Project I created an end-to-end CI/CD pipeline while keeping in mind Securities Best Practices, DevSecOps principles and used all these tools *Git, GitHub , Jenkins,Maven, Junit, SonarQube, Docker, Trivy, AWS S3, Docker Hub, Kubernetes , Slack and Hashicorp Vault.*  to achive the goal.


## Project Architecture
![](https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Images/architecture.png)

### PreRequisites
1. JDK 
1. Git 
1. Github
1. Jenkins
1. Sonarqube
1. Docker
1. Trivy
1. AWS account
1. Docker Hub account
1. Minikube & Kubectl
1. Hashicorp Vault
1. Slack

## Want to create this Project by your own  then *Follow these  project steps*

### Stage-01 : Install JDK and Create a Java Springboot application
Push all the web application page code file into github

![](https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Images/code.png) 

### Stage-02 : Install Jenkins and start Jenkins 
1. Installation guide is available here  https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Jenkins_installation.md
1. After installation, install suggested plugins
1. Open Jenkins Dashboard and install required plugins – SonarQube Scanner, Hashicorp Vault, Slack
1. go to manage jenkins > manage pulgins > search for plugins > install without restart
![](https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Images/jenkins.png) 

1. We will required another pulgin called - Kubernetes Continuous Deploy Plugin ( this plugin is deprecated but we can down grade the version for just testing purpose)
Download the Plugin file from here https://github.com/praveensirvi1212/DevSecOps-project/blob/main/kubernetes-cd.hpi
1. Now go to manage jenkins > manage pulgins > Advanced Setting > Deploy Plugin > choose the download file ( kubernetes-cd.hpi) > click on Deploy
![](https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Images/plugins.png) 

### Stage-03 : Install Postgre Database and Install SonarQube
1. Installation guide is available here https://github.com/praveensirvi1212/DevSecOps-project/blob/main/sonarqube_installation_with_postgres_database.md
1. Create a Project Manually
1.  Give name to your project , Project key then click on setup
1.  Click on other ci and generate token
1.  Copy that token and save somewhere because we need this token later.
![](https://github.com/praveensirvi1212/jenkins_sonarqube_basic_project/blob/main/images/Screenshot%20from%202023-02-16%2012-47-08.png) 

### Stage-04 : Install Docker and Create DockerHub account
1. Installation guide is available here https://github.com/praveensirvi1212/DevSecOps-project/blob/main/docker_installation.md
1. Create DockerHub account 

![](https://github.com/praveensirvi1212/DevSecOps-project/blob/main/Images/dockerhub.png) 


### Stage-05 : Install Trivy for Vulnerability Scanner for Containers and other Artifacts
I am following  Debian/Ubuntu  based installation guide you can choose accourding to your os

```sh 
   sudo apt-get install wget apt-transport-https gnupg lsb-release
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
   ``` 
#### After trivy installation you can scan Container Images, FileSystem, Git Repositories
In our can we will scan contianer images

```sh 
   trivy image [YOUR_IMAGE_NAME]
   ``` 

### Stage-06 : Install Hashicorp Vault server 
1. Installation guide is available here https://www.cyberithub.com/how-to-install-hashicorp-vault-on-ubuntu-20-04-lts/

### Stage-07 : Install Slack
Install Slack from official website of Slack https://slack.com/intl/en-in/downloads/linux


### Stage-08: Install Minikube
Minikube installation Guide is Available here  https://www.linuxtechi.com/how-to-install-minikube-on-ubuntu/
