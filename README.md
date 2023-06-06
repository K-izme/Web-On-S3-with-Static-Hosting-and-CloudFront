# S3 with Static Hosting and CloudFront

## Diagram:

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/df2c0406-768f-4523-bcd9-7a38fbde6481" alt="Deploy" width="50%" height="50%">

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

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/3719b8ce-ea3d-474c-b666-9e97e1956920" alt="image" width="50%" height="50%">

Create a bucket and set up it as public because our permission on Sandbox is limited

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/9597d4b0-f344-47ab-bcec-3769f8c51239" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/43b3dc70-fb40-478a-97de-160dcebc1e1e" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/e4199fbd-fdbb-440b-9b00-3610a428beba" alt="image" width="50%" height="50%">

Upload our folder which is contain our web source, make sure tick it as public

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/39137a84-c8c2-4f72-9208-8dc3b0b4de9a" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/e9600f2f-5854-4ab8-abd6-1448b5052d20" alt="image" width="50%" height="50%">

Make sure to enable static website hosting

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/74f24965-48a6-46a7-9512-fc9a34224604)" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/a0028609-8204-4646-96db-efab514b61d6)" alt="image" width="50%" height="50%">

Edit ACL (we can also edit Policy at Permission page)

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/37826b3b-453c-4b9d-a99c-21efad34dac6" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2397fde2-0f3a-422e-a202-b6a2c56d7fd1" alt="image" width="50%" height="50%">

## Result HTML file

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/9e67924c-3786-4790-8aee-79c9faa4f18d" alt="image" width="50%" height="50%">

## In Route53

Now we make a record to route that www.xxxxxxx.io will be redirect to our S3 static website

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/9a103883-1ae1-4a7b-9962-3c95c3f896e5" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/da67a3a1-ecf0-41c9-a51e-44fd4e936ed8" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/29bc1709-7115-4bbd-9f91-9f5382a3e642" alt="image" width="50%" height="50%">

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/2c6e1c1c-7a55-4081-bf32-56e28a8e0fba" alt="image" width="50%" height="50%">

## To manage or create a certificate

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/f8bced3c-ebb1-4756-b6b2-686259af4447" alt="image" width="50%" height="50%">

## In CloufFront

We just need to care about this

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/0ea70262-6528-40a4-9a13-c0d016f8e461" alt="image" width="50%" height="50%">

And choose your certificate

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/6a5575fc-f398-4b15-9488-b262fa229ac4" alt="image" width="50%" height="50%">

We can simply understand about cloudfront cache:

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/bbeffc38-76f4-4b01-a26f-69c70b9947f7" width="50%" height="50%">


## Then edit in Amazon S3

<img src="https://github.com/K-izme/Web-On-S3-with-Static-Hosting-and-CloudFront/assets/91515708/4036f386-37b0-4a4d-a2ce-ae1c491a5a77" alt="image" width="50%" height="50%">

Our connect to website is now secure by HTTPS
