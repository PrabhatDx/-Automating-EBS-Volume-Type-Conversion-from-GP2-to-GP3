# -Automating-EBS-Volume-Type-Conversion-from-GP2-to-GP3
I'm excited to share a step-by-step guide on automating the conversion of newly created GP2 EBS volumes to GP3 using Amazon CloudWatch Events, AWS Lambda, and Python Code. This automation can help optimize performance and cost efficiency in the AWS environment. Here's how I set it up:

Step 1: Create an IAM Role for Lambda
Navigate to the IAM Console and create a new role with AmazonEC2FullAccess and CloudWatchEventsFullAccess policies. Name it Ebs_Volume_check.

Step 2: Create a Lambda Function
Navigate to the Lambda Console and create a new function named ConvertGP2toGP3 with Python 3.12 runtime.
I have attached the IAM role created earlier to this function
Deploy the Lambda function.

Step 3: Create a CloudWatch Event Rule
Navigate to the CloudWatch Console and create a new rule.
Select EC2 as the event source and choose the EBS Volume Creation event.
Add the Lambda function (ConvertGP2toGP3) as the target.
Name the rule and create it.

Step 4: Test the Setup
Create a GP2 EBS Volume via the EC2 console.
Verify the Conversion: Ensure the volume has been converted to GP3 after a few minutes.
