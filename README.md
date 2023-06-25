# aws_s3_static_website  




For this example we will create 2 buckets in AWS
First bucket name : dzzy.static.website
Second bucket name: www.dzzy.static.website

When trying to access the first bucket , we will be redirect to the second one. For the second bucket we have the reverse case.  

Create both bucket in the same region.  

Once our buckets are created, we have to bundle our ReactJs applications so that we can upload the result to the S3 buckets.

npm run build  

After this procedure, upload the content to the buckets. Once upload process finished, you need to modify the bucket access policy. To do so go the Permissions tab.  

In the bucket having the name www.dzzy.static.website   

We must attach the S3 bucket policy that you will find in the s3-bucket-policy.json file.  This will make accessible all content inside the bucket. 
Then we have to go to the settings section as activate the Static host option.  

To follow along make sure you already have registered and set up a domain on AWS. To make so , you have to use the Route53 service in  AWS. 
Route53 is a service that will allow you to register domain names. 
Define endpoints that will allow you to redirect users in case they hit that endpoint to a given application.  

As for last step, if for the moment we do not want to add SSL to the connections done to our website. We can skip the CloudFront step. 

For furthere information on how to setup a domain on AWS please check the following [video](https://www.youtube.com/watch?v=5IfDzpkLlYY&ab_channel=BeABetterDev).


CloudFront allow us to have HTTPs in our application. 
