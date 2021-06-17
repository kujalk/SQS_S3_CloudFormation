A CloudFormation template to create following resources,
- A SQS queue
- A S3 bucket with encryption enabled
- A bucket notification for created S3 that notifies SQS queue when new files are created
- An IAM role that can be assumed by EC2 to access the bucket and the SQS queue
- An EC2 with the above role attached

Instruction
-------------
- There are 2 templates defined. Create the stack in following order,
    1. S3_SQS_Role.yaml
    2. EC2.yaml
- Make sure you empty the S3 bucket before deleting the stacks
- Delete the stack in the following order (Because 1st stack references the output from 2nd stack)
    1. EC2.yaml
    2. S3_SQS_Role.yaml

Developer - K.Janarthanan