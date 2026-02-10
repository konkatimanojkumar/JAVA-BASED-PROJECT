
# Automated CI/CD Pipeline for Java Application 

> Project Overview

*  This project demonstrates an end-to-end CI/CD pipeline for a Java application using git ,GitHub, Jenkins, Maven,  Tomcat10, deployed on AWS EC2 servers.
*  The pipeline automates continuous download, build, test, and deployment to QA(testing) and Production environments.



# Project Architecture

  Servers Used (AWS EC2 instance)(ubuntu servers)

* Jenkins Server – CI/CD automation
* QA Server – Application testing (Tomcat10)
* Production Server – Live deployment (Tomcat10)

  

* The complete pipeline automatically handles:

     Code download from GitHub by using git commands 
     Build and packaging using Maven lifecycels
     Automated testing
     Deployment to QA environment
     Final deployment to Production environment



* Infrastructure (AWS Cloud)

  The project is deployed on AWS EC2 instances, separated by responsibility to follow real-world DevOps architecture.

   Jenkins Server: Manages CI/CD pipeline
                   Pulls code, builds, tests, and deploys

    QA Server:  Hosts application for testing
                Used for validation before production

    Production Server: Hosts live application
                       Accessible to end users

  
Software Installed on Servers

Jenkins Server:
              openjdk-17-jdk
              Git
              Maven
              jenkins
              Required Jenkins plugins (Git, Maven, Deploy to Container)

QA & Production Servers:
               tomcat10
               tomcat10-admin
               Application credentials configured in tomcat-users.xml

                   

Tools & Technologies Used

Version Control	     Git, GitHub
CI/CD Tool	         Jenkins
Build Tool	         Maven
Application Server	 Apache Tomcat 9/10
Cloud Platform	     AWS EC2
Language	            Java


Complete CI/CD Workflow

1) Code Development & Version Control
        Developers write Java application code.
        Code is pushed to a GitHub repository.
        Any new commit automatically triggers the Jenkins pipeline.

2) Continuous Integration (CI)
        Jenkins pulls the latest code from GitHub.
        Jenkins integrates with Git and Maven plugins.by using git plugins jenkins auto perform  "Continuous Download"
        Maven lifecycle is executed:
                  validate
                  compile
                  test
                  package
       A deployable artifact (WAR file) is generated.by using maven plugins jenkins auto integrate with maven and execute   "Continuous Build" stage

4) Artifact Management
         The generated artifact is stored temporarily within Jenkins workspace.
         The same artifact is used across QA and Production to maintain consistency.

5) Automated Deployment to QA Environment
         jenkins connects to the QA Tomcat server. by the creditionals which we are created inside the tomcat-user.xml file
         Credentials are securely configured in Jenkins.
         Jenkins deploys the artifact using Deploy to Container plugin.
         Application becomes available on:
                        http://<QA-PUBLIC-IP>:8080

5️) Continuous Testing
          Jenkins triggers automated test scripts. it will download first and execute the script on the application which is running on QA server
          Validates application functionality after deployment.
          Ensures application stability before production release.
          

6️) Automated Deployment to Production
           If QA testing is successful:
           Jenkins automatically promotes the same artifact.
           Deploys it to the Production Tomcat server.
           Application becomes live with zero manual intervention.



Project Outcome

  Continuous Download,
  Continuous Build,
  Continuous Deploy,
  Continuous test,
  Continuous Delivery.

Jenkins automates the entire software delivery lifecycle from code commit to production release.


























                   
                   
