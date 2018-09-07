# Overview

## Scope
There are two cloud formation templates:
* cf-jenkins-linux - installs a jenkins instance on an ubuntu (linux) based ec2 instance
* cf-linux-windows - install a jenkins instance on an windows based ec2 instance

## Instructions 
* Using one of the cloudformation templates 
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
* Done 