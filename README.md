# AWS S3 (Simple Storage Service)

S3 is like a virtual drive to store and retrieve data. According to the AWS definition, “You can use Amazon S3 to store and retrieve any amount of data at any time, from anywhere on the web."

```
- Files in S3 are stored in buckets ( Buckets are like folders )
- S3 is object-based storage (Like Images, videos, documents etc)
- Buckets names should be unique globally because when we create a bucket in S3 it will have a unique URL.
- Its a good practice create buckets in the nearest region to you or for your customers.
```

The five majoor advantages of S3:

- Availability & Durability
- Scalability
- Security
- Cost Effective
- Performance

```
- S3 provides bucket policies, access control, and encryption settings that are appropriately configured. 
- Encrypt data at rest using server-side encryption options provided by S3. Additionally, enable encryption in transit by using SSL/TLS for data transfers. 
- Enable access logging to capture detailed records of requests made to your S3 bucket. 
- Monitor access logs and configure alerts to detect any suspicious activities or unauthorized access attempts. 
- S3 provides features and configurations to assist with compliance requirements, such as enabling Object Lock for data immutability, managing legal holds, and integrating with AWS CloudTraiI for audit trails. 
```
![image](https://github.com/Pavan-1997/AWS_S3/assets/32020205/2742ddc9-ead5-45e7-8185-a03c805f6651)
---

# TASK1- RESTRICT A USER FROM ACCESSING THE AWS OBJECT, YET USER IS HAVING ACCESS TO S3 BUCKET FROM IAM 

1. Create a S3 bucket and add any object 

2. Now goto IAM -> Create a user -> Check provide user access to AWS … -> Select I want to create an IAM user -> Give a custom password -> Uncheck user must create a new password …( just to save time to login) -> Next

3. Go back to the user -> Goto Permissions -> Add Permissions -> Attach policies directly -> Search and below policies - AmazonS3FullAccess ->  Click on Next -> Add Permissions -> Now the user can see all the buckets and can download the objects

4.  Now go back to the root user bucket permissions of the created bucket -> Go to the bucket policy and click on edit  -> Use below code
	
5. Now login to the AWS console using the user we created earlier and try to access the bucket which should show as Insufficient permissions to list objects

![USER_S3_PERMISSION](https://github.com/Pavan-1997/AWS_S3/assets/32020205/b7a95811-12f4-4bf4-a349-b344d2b01f88)

---

# TASK2 - HOST STATIC WEBSITE

1. Add a simple HTML file to the bucket 

2. Goto the bucket properties and click on static website hosting -> Enable -> Give name for the html file uploaded -> Save changes

3. Now if we try to access the URL we will be getting a 403 Forbidden error

4. Now goto bucket permissions -> Click on Edit Block public access (bucket settings) -> Uncheck Block all public access -> Click on Save changes -> Confirm 

5. Yet again the access will be denied 

6. Now goto the Bucket Policy and replace the old policy with the below one

![STATIC](https://github.com/Pavan-1997/AWS_S3/assets/32020205/a1c0824c-048c-41a2-b692-bda7d824633e)







