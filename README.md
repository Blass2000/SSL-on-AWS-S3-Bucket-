# SSL-on-AWS-S3-Bucket-
Project directives and steps for configuring SSL on an S3 in AWS
Configuring SSL on EC2 using AWS certificate Manager



Introduction : In this article I have shown to how we can use AWS certificate manager to configure ssl on EC2

Step1 : We will go to the Route 53 console.

Under that we will select the Hosted zone

Under that we will select the Created Hosted zone

Under that we will give the our domain name 

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/09966562-bbc7-4b4f-83b5-f7953d7acb39)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/6352c0b2-ee44-4e1f-bcc7-434364cc79ba)


Step2 : We will update the Name servers of our Domain in Route 53

For doing this we will login into our Domain Provider . In my case it is Hostinger

Under that we will go to the Domain/Name server option.

Under that we will click on the Change Name server option following the window option will appear . We will select the Change Name Server option and under that we will copy the Hosted zone name server records into name server details like given below

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/959328ec-ff21-4a21-bb85-b299da8b2bf5)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/aae52787-4f90-4af1-bf65-e9d1275ac423)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/73ca128e-e401-4506-929e-720ccfbf3396)


Step 3 : Requesting SSL certificate from AWS certificate Manager

Go to Certificate Manager in Services. Now, click on Request a Certificate. Then Select the default option of public certificate and click on Next.


![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/d1470cbc-c568-4c30-975d-58595f9c4192)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/e5cbedd1-94de-41f7-b1b5-61fad1a60fd0)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/f80513e2-b921-47fe-9f22-5bbe250569e4)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/5ae903ed-69b0-4535-a039-c6a85400c74f)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/18a222e5-ccdd-4b21-baa8-79b8d53280c5)

![image](https://github.com/Blass2000/SSL-on-AWS-S3-Bucket-/assets/89789502/2b1bfca0-ee02-4e77-b979-0c2f8f28bf01)


Step 4 : Launching EC2 instance

We will go to the EC2 instance and we will click on launch EC2 instance

We will enter the instance name and select ubuntu as window and select security group which we have created and key pair also for connecting the instance ,





Step5: Create the Target Group

For doing this we will click on Target Group option under elastic load balancing option Following window will appear





Step 6 : Creating LoasBalancer

We will click on load Balancer under load balancer option






Step 7 : Installing the Apache in Our EC2

Now we will connect to our EC2 server and install apache on it

sudo apt update

sudo apt install apache2


When we are hitting the dns of the load balancer with following url it shows following things


Step 8 : Configuring Record of LoadBalancer on Route 53 and Directing to HTTPS

Go to Route 53

Under that Go to Hosted zones

Under that we will go to raghu.cloud and click on Create Record

Following window will appear

We will click on create record

When we hit the following url it will run on https

