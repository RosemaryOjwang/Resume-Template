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
4. Unselect 'Block all public access'. This will enable anyone on the internet to access the bucket with your resume.
5. Scroll down and choose 'Create'.
![Create bucket](<Create Bucket.png>)

### Step 2: Enable static website hosting for your bucket

1. Click on 'Buckets' on the left of your Amazon S3 Console window to access a list of your buckets.
2. Click on the name of the bucket you created above, to view the bucket's details.
3. Choose 'Properties'.
4. Scroll down to 'Static website hosting' and choose 'Edit'.
5. Under 'Static website hosting' choose 'Enable', and choose 'Save changes'.
6. Under 'Index document', enter the name of the default page of your website: index.html
7. Scroll down and choose 'Save changes'.
![Enable static website hosting](<Enable static website hosting.png>)

### Step 3: Add a bucket policy for public read access to the bucket's content
1. While still in your bucket details view, choose 'Permission', just next to 'Properties'.
2. Scroll down to 'Bucket policy' and Click on 'Edit'.
3. Enter bucket policy in the Bucket policy editor (as is in the screenshot below) to grant public read access for your website.
![alt text](<Bucket policy for public read access.png>)
P.S: 'resume-bucket-ojwang' is the Bucket-Name.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}
```
4. Choose 'Save changes'.

### Step 4: Upload website content to S3
1. While still in Amazon S3 console, select 'Buckets' on the left side of your screen.
2. Click on the name of your bucket, in the buckets list that shows on the main section of your screen.
3. Click on the 'Upload' button on the right side of your screen to upload your website's files/folders.
4. Click on 'Add files' or 'Add folder', depending on what you have for your website, and select the respective file or folder for your website.
5. Scroll down and click on 'Upload'.

### Step 5: Create an Amazon CloudFront Distribution
1. Search for and select 'CloudFront' from 'Services'.
![alt text](<CloudFront Nav.png>)

#### Step 6: Test your website endpoint
1. Click on 'Buckets' on the left side of your Amazon S3 console screen.
2. Click on the name of your bucket.
3. Click on 'Properties'.
4. Scroll down to 'Static website hosting' section and click on 'Bucket website endpoint' link at the very bottom of the screen.

![alt text](<website endpoint.png>)


## References
- [Tutorial: Configuring a static website on Amazon S3
](https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html)

- [Hosting HTML Pages Using AWS S3 and CloudFront: A Step-by-Step Tutorial](https://medium.com/@fabiokndt/hosting-html-pages-using-aws-s3-and-cloudfront-a-step-by-step-tutorial-8149476b11b4)

## Licenses
[MIT](https://opensource.org/license/mit)

_Copyright (c) 2024._ **By Rosemary Ojwang**
