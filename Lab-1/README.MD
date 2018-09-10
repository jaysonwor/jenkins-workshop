# Overview
Jenkins Workshop

## Scope
These Lab-1 exercises will get you familar with a basic pattern for grabbing and building (or in our case executing) code on a target server, using Jenkins server.

## Instructions 
### Simple Exercise 
* Open the Jenkins URL (found in setup) 
* Create a new job (new item)
* Enter a unique item name and choose freestyle project 
* Configure this job to 
    * Checkout using GIT (Source Code Mgmt) from your forked GitHub repository (during setup)
    * Specify build instructions (either CMD (Windows) or SH (Windows) command) to start a simple http server 
* Run the job and validate you can hit the web browser url

### Advanced Exercise
Being able to create a jenkins job using the UI is good, but doesn't scale, the real power comes from Jenkins ability to define a job/pipeline in code (I.E in a Jenkinsfile). More can be found on jenkins pipeline here: https://jenkins.io/doc/book/pipeline/
* Once you get the basic freestyle Jenkins job working migrate to using a declarative jenkins pipeline
* Create a new job (new item)
* Enter a unique name and choose pipeline 
* Follow a similar set of instructions as before but instead implement as a pipeline script or pipeline script from SCM

### Caveats & Gotchas
* You may either use the .py code sample provided under code-samples or write your own
* Note: if you run this script in the job the job will never terminate. Feel free to figure out how to run the background, or just kill the job every time... 
* if you are using the sample code provided you may notice its running a web server on port 8000, which may not be exposed as an inbound rule in the security group... this will need to be solved either in the cf-jenkins-windows or cf-jenkins-linux cloudformation template (preferably) or manually in the console