# Getting Started 
This project contains cloudformation templates for installing and configuring jenkins (and dependencies)

## Prerequisites
* An existing AWS Account is required
* A KeyPair (pem) file has already been created in AWS/EC2 and locally accessible
    * more can be found on this topic here: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html
* An account with GitHub 

## Installing Jenkins for Linux 
* Open the AWS Console and navigate to the CloudFormation service
* Click Create Stack and select an existing template to upload
    * choose the cf-jenkins-linux.json file
* Click Next
* Input a unique stack name and existing KeyPair from the drop down (keypair was created as part of the prerequisite above)
* Click Next past the next two screens and finally Create
* During the cloudformation create you'll see one of the following statuses:
    * CREATE_IN_PROGRESS: building the necessary resources 
    * CREATE_FAILED or ROLLBACK_COMPLETE: failed to create the resources 
    * CREATE_COMPLETE: resources have been built and environment ready 
* Upon CREATE_COMPLETE navigate to the "Outputs" tab to get the URL for Jenkins 
* Done (move onto PostInstall for Linux)
    * Note: May take an estimated 30secs after cloudformation completes before instance is available (URL is accesible)




## PostInstall for Linux
* Default Password Retrieval
    * Upon successfull completion of the cloudformation template navigate to the "Resources" tab in the CloudFormation screen
    * Click the EC2Instance's Physical ID link which will naviate to the cooresponding EC2 instance
    * Click Launch Instance which will provide instructions for (ssh) connecting to the instance (note use the pem file that was associated during the cloudformation creation)
    * At the terminal input: sudo cat /var/lib/jenkins/secrets/initialAdminPassword to retrieve the password

    