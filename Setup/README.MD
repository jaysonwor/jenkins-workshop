# Overview
Jenkins Workshop

## Scope
There are two cloud formation templates:
* cf-jenkins-linux - installs a jenkins instance on an linux based ec2 instance
* cf-linux-windows - install a jenkins instance on an windows based ec2 instance

## Instructions 

### GitHub Setup
* Login to your github account and navigate to this repository
* Click the fork button to fork this repository in your github workspace (very important only use your forked repository beyond this point)

### Jenkins Install (Linux)
* Using the "cf-jenkins-linux" cloudformation template
* Open the AWS Console and navigate to the CloudFormation service
* Click Create Stack and select an existing template to upload
    * choose the cf-jenkins-linux.yml file
* Click Next
* Input a unique stack name and existing KeyPair from the drop down (keypair was created as part of the prerequisite above)
* Click Next past the next two screens and finally Create
* During the cloudformation create you'll see one of the following statuses:
    * CREATE_IN_PROGRESS: building the necessary resources 
    * CREATE_FAILED or ROLLBACK_COMPLETE: failed to create the resources 
    * CREATE_COMPLETE: resources have been built and environment ready 
* Upon CREATE_COMPLETE navigate to the "Outputs" tab to get the URL for Jenkins 
* Done 

### Jenkins Install (Windows)
* Using the "cf-jenkins-windows" cloudformation template 
* Open the AWS Console and navigate to the CloudFormation service
* Click Create Stack and select an existing template to upload
    * choose the cf-jenkins-win.json file
* Click Next
* Input a unique stack name and existing KeyPair from the drop down (keypair was created as part of the prerequisite above)
* Click Next past the next two screens and finally Create
* During the cloudformation create you'll see one of the following statuses:
    * CREATE_IN_PROGRESS: building the necessary resources 
    * CREATE_FAILED or ROLLBACK_COMPLETE: failed to create the resources 
    * CREATE_COMPLETE: resources have been built and environment ready 
* Upon CREATE_COMPLETE navigate to the "Outputs" tab to get the URL for Jenkins 
* Done 

### Jenkins Post-Install Setup (Windows)
* Unfortunately there isn't a scripted setup of the tools so the following must be done manually via RDP
* Download and Setup JDK8+ http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
* Download and Setup Jenkins https://jenkins.io/download/

### Jenkins Plugin Configuration (Both Windows & Linux)
* Open Jenkins URL
* Click Manage Jenkins (left nav)
* Click Manage Plugins 
* Click Available tab
* Filter/Search for "Git", (without quotes... may have to scroll down a bit since there are many) select it, and choose install without restart
* Filter/Search for "Pipeline ", (without quotes... may have to scroll down a bit since there are many) select it, and choose install without restart