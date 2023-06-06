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

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2e3687e7-9d91-40c9-ba7b-30375f8cc2dc" alt="image" width="50%" height="50%">

Create a bucket and set up it as public because our permission on Sandbox is limited

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/7ffc7780-e937-4b67-8876-aa3ba3f4de27" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/883be8a3-1a12-41ad-8081-1b5bfd083896" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/88494836-59da-4b1b-91a1-d9d7ea795fde" alt="image" width="50%" height="50%">

Upload our folder which is contain our web source, make sure tick it as public

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2782c03c-cedb-4648-9b1d-81323c53218e" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/450cb1a4-da7a-446f-ab23-42bdeeee861d" alt="image" width="50%" height="50%">

Make sure to enable static website hosting

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/ebb04b18-f222-494a-8c80-f8fe155a6cd4" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/c7cdc8e4-8415-4313-b3e0-261bbd29c6e8" alt="image" width="50%" height="50%">

Edit ACL (we can also edit Policy at Permission page)

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/40a248cd-5533-4487-a6e2-172db7aca2ae" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/1f4e79c5-ded1-49bd-a4e5-c2c5e6493fdb" alt="image" width="50%" height="50%">

## Result HTML file

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/207034ef-a38a-429c-84eb-bfb1145fb174" alt="image" width="50%" height="50%">

Now we make a record to route that www.xxxxxxx.io will be redirect to our S3 static website

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/442f87ac-9fcb-4713-b73f-95fe2b3e170c" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/fd9a83d0-d6fb-4858-a0ba-d27e51c73d68" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/da62873a-c6a7-4de8-99f9-31caeb0bf899" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/4042f8a9-5346-44f9-80b7-381d049b3d63" alt="image" width="50%" height="50%">

## To manage or create a certificate

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/f0a24524-2627-4281-94ed-2b20d03661cb" alt="image" width="50%" height="50%">

## In CloufFront

We just need to care about this

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/8f751fca-fb8c-470b-a8d1-04a50fd772ed" alt="image" width="50%" height="50%">

And choose your certificate

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/0598c382-1bd6-4932-8ed0-d23ae7c3cb79" alt="image" width="50%" height="50%">

We can simply understand about cloudfront cache:

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/9752fe0c-99b2-40a4-ba79-4c3268b315b0" alt="image" width="50%" height="50%">


## Then edit in Amazon S3

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/df9677df-c399-4692-8be6-cd5cb9417968" alt="image" width="50%" height="50%">

