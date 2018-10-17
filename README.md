# project-k8

Kubernetes Project Dev to Production

As a product owner I want a infrastructure which is running in cloud and having kubernetes cluster running. 

My application is java based microservices which need to build & deploy on Kubernetes cluster environment.

# CI/CD #
Jenkins should be configured as master and slave where master is only to create the build and deployment job, all build and deployment job should run on slave. 
Use Jenkins pipeline for build & deploy the application. 

[It would be great if slaves are in on-demand  this is not in phase 1 but it requires in future.]

# Test result & Artifactory #
Configure sonar for test cases analysis and use Nexus as artifactory repository.

# Monitoring  #
Configure ELK to monitor pod’s and server logs. 
Configure Grafana to monitor the applications which are running on pod’s -- basically monitor the jvm and application health.

# DB # 
 DB should be mongo db which are running on standalone machine as cluster mode. 

Acceptance Criteria 

Jenkins Pipeline jobs should be created as jenkins dsl plugin. 
Use groovy script or Jenkins file approach to create all jenkins build and deployment job
Checkmarx should be run at the time of build creation [https://wiki.jenkins.io/display/JENKINS/Checkmarx+CxSAST+Plugin ]
Build should have versioning so we can deploy the exact version of image to any environment
There will be revert facilities of build if deployment goes wrong or unstable we can run the stable build or older build.
Write Ansible scripts to deploy the application on all environments 
All build and deployment should be parameterised [Branch name , Build number, Image id or version ]
	Note : 

              User can choose the parameters to create the build and deployment
     Parameters for Build : branch name 
     Deployment parameters : Image_Snapshot_version
     Environment : Dev/QA/Prod
  

There will be stages like 


Dev - Job

Build → Image Build → Image Deploy on Dev → Image Promote → Send Notification

QA - Job 

Deploy Image → Send Notification

Prod - Pipeline - Job

Code Build from master/Git- Tag → Image Build → Image Upload to artifactory Repository → Image Deploy → Send Notification.




Performance Test Before Production 

Use Jmeter and Taurus before send the code to Production, As we all know production is something where we should prepare for everything. Means our infrastructure as well as our application should be capable enough to take the load of unexpected user count. 

So before making website live on production just do a performance test using Jmeter & Taurus. 
These two tool should be integrated with jenkins and make it independent we can only running these tools when required , we are not going to install it on jenkins master or any slave. 

So configure it on the way like on a standalone or any particular pod so if we want to run load more than 10K user simultaneously we can run on demand.

Tools : JMeter & Taurus  → Integration with Jenkins → Result should be print on Blazemeter website.





#########################################################

Steps & command to setup K8 Cluster

Test Update by Sara
=================================

2nd Test Update by Sara
=================================





