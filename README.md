# Automated Image Resizing and Transfer System Using AWS Services

## Project Description:
This project focuses on building an automated system for image processing and management within the AWS ecosystem. The goal is to streamline the handling of images by automatically resizing them and transferring them to a designated storage location while keeping stakeholders informed through notifications. Key AWS services, such as Lambda, S3, and SNS, are used to orchestrate this workflow.

## Key Features:
1. Image processing automation: Automatically resize and optimize images upon upload.
2. Secure storage: Store processed images in a secure and reliable S3 bucket.
3. Real-time notifications: Receive immediate updates about image processing via SNS.
4. Scalable architecture: Design for scalability to handle image processing demands.
5. Cost-efficient solution: Leverage AWS serverless technologies to minimize operational costs.

## Overview :

![a1](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/d806e90a-365e-4f59-a6ac-2606c74b79e3)



## Steps :
### Step 1 :
### Creating Source and Designation s3 Buckets :

1. Navigate to the S3 Console.

2. Create the destination bucket using the same steps and name it with a unique name.

### Step 2 :
### Creating the SNS Notification :

1. Navigate to the SNS console.
   
3. Scroll down and Click "Create subscription" <br>
4. After this , you will receive some mail for Subscription Confirmation and you have to confirm that.<br>
5. You can use any other protocols also like SQS, HTTP, SMS etc .,<br>

### Step 3 :
### Creating the Lambda :

Navigate to the Lambda Console.

Now replace the default code with the image-resizing-s3.py and deploy the changes , Don't test the code now we have to do some more actions before testing.
   
After that , We have to give some permission for our Lambda Function to do our process (resizing).

Now we have to trigger the function.


![i26](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/166aadb1-4d3a-40d8-a70e-681ea507e1d1)


![i27](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/b8dcb311-1914-47bc-96a7-5df62a283954)


![i28](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/76164aba-a478-4590-a7e4-966d3f30078f)


7. Now we have to go to code section , and scroll down to  layers.<br>
8. We have to add layer .<br>
9. May be you can think , why ?<br>
10. It's because for resize the image we upload in our source S3 bucket , We need a python library called pillow in our code to resize the image . We can manually add Pillow library also, But it's very time consuming and you have to do lot more , Instead of manually adding pillow library we are going to use layers for Some easy action.<br>
11. Follow the outlined Steps below.


![i51](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/a4500c08-8a18-4a26-844a-5ad7712ba310)


![i52](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/d20cb878-d8a9-4757-8f42-7596f5448f0f)
12.You can copy the arn from below.

```
arn:aws:lambda:ap-south-1:770693421928:layer:Klayers-p39-pillow:1
```

13. After done all the actions above , now we can test our code.

14. It will show some results like below , It runs successfully but return some error because we still not upload the images in S3 yet.

### Step 4 :
### Results :

1. Navigate to the S3 Console.
2. Upload Some images in  Source Bucket.

### It Successfully resized the Image and sends me the Notification.


