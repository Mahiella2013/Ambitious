# Ambitious
Purpose:
--------
To maintain all my learnings and findings.

Assignment 1:
-------------
Create a API using Lambda function and write the output to an object. Upload the file to S3. Following are the steps taken to complete this assignment.
1. Completed an e-learning on Lambdafuntion and API-Gateway integration briefly
2. Created an AWS account and faced account confirmation issue, which was resolved after raising a ticket with AWS.
3. Created S3 bucket and made it public adding relevant bucket policy so that objects can be transferred.
4. Followed steps as per the details given in AWS tutorial.
5. As per the assignment customized the code, which are as follows
   5a. Used putObject method to create a file with the API response and move it to the S3 bucket
   5b. Used callback function instead of async as putObject did not work with async. 
6. Learning - Entire JSON response should be returned instead of the property of a JSON object. There was not much information given in the console or in the internet. Later found that there is a fearture called "Test" within the API-Gateway, which provided detailed log. That helped to fix the issue.Also, there was a lot of trial and error done. API-Gateway URL: https://pkyjft3am6.execute-api.us-east-1.amazonaws.com/default/helloWorld

Deploying Lambda function through serverless framework:
--------------------------------------------------------
1. Prerequisites: Install nodejs, npm, aws-sdk, visual studio code and serverless tool to create, run, debug and deploy the Lambda function from CLI.
2. Create an aws config file using the command "sls configcredentials --provider aws --key {} --secret {}"
3. Using a serverless command "sls create --template aws-nodejs" create a service from the available templates. I used "aws-nodejs" template.
4. Using visual Studio code, handler.js was created with the Lambda function "helloWorld" and the deployment configuration was set up in serverless.yml file,which provisions resources like S3,API-gateway and deploys Lambdafunction through a cloud formation template and stores all the details in the S3.
5. On completing the above set up, tested the function on my local machine via CLI using the command "sls invoke local --function helloWorld", which provided the below output\
{\
    "statusCode": 200,\
    "body": "Hello World on 24/9/2019 @ 21:5:18 !!"\
 }\
 hi-------> { Bucket: 'my-pppractice-bucket',Key: 'Hello5.Txt',Body: 'Hello World on 24/9/2019 @ 21:5:18 !!' }\
 Successfully saved object to my-pppractice-bucket/Hello5.Txt\
6. As the outcome was expected, I started to deploy the function in AWS console using the command "sls deploy", which provisioned the necessary resources in my AWS account with the following output\
 Serverless: Packaging service...\
 Serverless: Excluding development dependencies...\
 Serverless: Uploading CloudFormation file to S3...\
 Serverless: Uploading artifacts...\
 Serverless: Uploading service serverlesscli2.zip file to S3 (665 B)...\
 Serverless: Validating template...\
 Serverless: Updating Stack...\
 Serverless: Checking Stack update progress...\
 ..............\
 Serverless: Stack update finished...\
 Service Information\
 service: serverlesscli2\
 stage: dev\
 region: us-east-1\
 stack: serverlesscli2-dev\
 resources: 9\
 api keys:\
    None\
 endpoints:\
    GET - https://rqu9hxmt98.execute-api.us-east-1.amazonaws.com/dev/hello    \\\
 functions:\
    helloWorld: serverlesscli2-dev-helloWorld\
 layers:\
    None\
 Serverless: Run the "serverless" command to setup monitoring, troubleshooting and testing.
