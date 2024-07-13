# Hosting a Static Resume Website on Amazon Simple Storage Service (Amazon S3)
  
## Description
_Resume Challenge is a step-by-step process of hosting a static resume website on Amazon Simple Storage Service(Amazon S3)._
Amazon S3 is an object storage service by AWS that offers scalability, security, data availability and performance.

## Architecture Diagram
![AWSArchitecture](AWSArchitecture.png)

## Prerequisite
- Create a HTML resume website and name the default page of the website as index.html.
- Ensure that you an AWS account.
![AWS Account](FreeTierAccount.png)

## Set-Up Procedure
- Sign in to AWS Management Console, search and select S3 under 'Services'.
![S3 Search](<S3 Search.png>)

### Step 1: Create a bucket
1. Click on 'Create bucket'.
2. Choose the Region where you want to create the bucket from.
3. Enter the 'Bucket name'. 
4. Scroll down and choose 'Create'.
![Create bucket](<Create Bucket.png>)

### Step 2: Enable static website hosting for your bucket

1. Click on 'Buckets' on the left of your Amazon S3 Console window to access a list of your buckets.
2. Click on the name of the bucket you created above.
3. Choose 'Properties'.
4. Scroll down to 'Static website hosting' and choose 'Edit'.
5. Under 'Static website hosting' choose 'Enable', and choose 'Save changes'.
6. Under 'Index document', enter the name of the default page of your website: index.html
7. Scroll down and choose 'Save changes'.
