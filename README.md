# S3 with Static Hosting and CloudFront

## Diagram:

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/31dcd4be-f63e-4057-891d-4b46f9e964b1" alt="Deploy" width="50%" height="50%">

## What is AmazonS3?

Amazon S3 (Simple Storage Service) is an object storage service provided by Amazon Web Services (AWS) which is designed to store and retrieve any amount of data from anywhere on the web. S3 is highly scalable, durable, and secure, making it suitable for a wide range of applications and use cases.

## What is Amazon Route53?

Amazon Route 53 is a scalable and highly available domain name system (DNS) web service provided by Amazon Web Services (AWS) which is used for DNS services. Route 53 helps to route end users to internet applications by translating domain names into IP addresses.

Key features: Domain Registration, Domain Management, Domain Routing, Traffic Management, DNS Security,...

## What is Amazon Cloud Front?

Amazon CloudFront is a global content delivery network (CDN) service provided by Amazon Web Services (AWS) which is designed to deliver content, including static files, dynamic content, and APIs, with low latency and high data transfer speeds. CloudFront helps improve the performance, scalability, and availability of web applications by caching content at edge locations closer to end users.

Key features: HTTPS, DDoS Protection, Edge Functions, Global edge network, ... 

## Static Hosting

In this we will create a domain www.xxxxxxx.io which will redirect to our storage service (will be a static website)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2e3687e7-9d91-40c9-ba7b-30375f8cc2dc)

Create a bucket and set up it as public because our permission on Sandbox is limited

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/7ffc7780-e937-4b67-8876-aa3ba3f4de27)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/883be8a3-1a12-41ad-8081-1b5bfd083896)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/88494836-59da-4b1b-91a1-d9d7ea795fde)

Upload our folder which is contain our web source, make sure tick it as public

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2782c03c-cedb-4648-9b1d-81323c53218e)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/450cb1a4-da7a-446f-ab23-42bdeeee861d)

Make sure to enable static website hosting

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/ebb04b18-f222-494a-8c80-f8fe155a6cd4)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/c7cdc8e4-8415-4313-b3e0-261bbd29c6e8)

Edit ACL (we can also edit Policy at Permission page)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/40a248cd-5533-4487-a6e2-172db7aca2ae)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/1f4e79c5-ded1-49bd-a4e5-c2c5e6493fdb)

## Result HTML file

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/7c5eeac3-3c88-410f-b5df-a99a4a9c213a)

Now we make a record to route that www.xxxxxxx.io will be redirect to our S3 static website

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/442f87ac-9fcb-4713-b73f-95fe2b3e170c)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/fd9a83d0-d6fb-4858-a0ba-d27e51c73d68)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/da62873a-c6a7-4de8-99f9-31caeb0bf899)

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/4042f8a9-5346-44f9-80b7-381d049b3d63)

## To manage or create a certificate

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/f0a24524-2627-4281-94ed-2b20d03661cb)

## In CloufFront

We just need to care about this

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/8f751fca-fb8c-470b-a8d1-04a50fd772ed)

And choose your certificate

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/0598c382-1bd6-4932-8ed0-d23ae7c3cb79)

We can simply understand about cloudfront cache:

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/9752fe0c-99b2-40a4-ba79-4c3268b315b0)


## Then edit in Amazon S3

![image](https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/df9677df-c399-4692-8be6-cd5cb9417968)

