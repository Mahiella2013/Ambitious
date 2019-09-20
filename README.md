# Ambitious
Purpose:
To maintain all my learnings and findings.

Assignment 1:
Create a API using Lambda function and write the output to an object. Upload the file to S3. Following are the steps taken to complete this assignment.
1. Completed an e-learning on Lambdafuntion and API-Gateway integration briefly
2. Created an AWS account and faced account confirmation issue, which was resolved after raising a ticket with AWS.
3. Created S3 bucket and made it public adding relevant bucket policy so that objects can be transferred.
4. Followed steps as per the details given in AWS tutorial.
5. As per the assignment customized the code, which are as follows
   5a. Used putObject method to create a file with the API response and move it to the S3 bucket
   5b. Used callback function instead of async as putObject did not work with async. 
6. Learning - Entire JSON response should be returned instead of the property of a JSON object. There was not much information given in the console or in the internet. Later found that there is a fearture called "Test" within the API-Gateway, which provided detailed log. That helped to fix the issue.Also, there was a lot of trial and error done. API-Gateway URL: https://pkyjft3am6.execute-api.us-east-1.amazonaws.com/default/helloWorld
