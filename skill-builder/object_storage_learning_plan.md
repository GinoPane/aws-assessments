## AWS Object Storage Learning Plan

#### Q1. A company is preparing for their global annual sales and learning conference. To get proper attention and registration they have built an event website that is stored in a static Amazon S3 bucket. The website contains a lot of web pages with rich visual and textual content. Marketing has asked IT operations to ensure that visitors to the website, from all over the world, get the content as quickly as possible. What is the most efficient and scalable way to achieve this requirement?

- [ ] Create a bucket with the website per region, and use Amazon Route 53 to direct the user to the closest region.
- [ ] Partition the website content to multiple buckets to improve the per-section performance.
- [x] Create an Amazon CloudFront Distribution and use the Amazon S3 bucket as the origin.
> Comments: This is exactly the scenario which Amazon CloudFront was designed to meet. Serve static content closer to the user.
- [ ] Use Amazon S3 Transfer acceleration to speed up loading of the content.

#### Q2. Your multi-threaded application running on an Amazon EC2 instance occasionally receives Status Code 503 responses when it tries to access objects in an Amazon S3 bucket. What does this indicate and how should you address it?

- [ ] Status code 503 indicates a malformed client request. Examine the code logic to find the error.
- [ ] Status code 503 indicates that an AWS Budgets action has been used to turn off access to the bucket. Check if a previously configured budget threshold has been triggered in your account.
- [x] Status code 503 indicates the Amazon S3 exception "Slow Down". Address this by implementing an exponential backoff and retry strategy for your access requests.
> Comments: “AmazonS3Exception: Slow Down (Service: Amazon S3; Status Code: 503; Error Code: 503 Slow Down”
- [ ] Status code 503 indicates that the request is Forbidden. Examine the access controls at the object level, and the code logic, to find the error.

#### Q3. How many versions can an object have when object versioning is enabled?

- [x] Unlimited versions.
> Comments: Objects can have unlimited versions.
- [ ] Up to 1024 versions of the same object.
- [ ] You can have up to 65535 versions of the same object.
- [ ] Up to 4 versions, after that you need to delete the older versions to continue adding new versions.

#### Q4. You are working on a new project using Amazon S3 multipart upload. How would you answer this question from a team member. What is the maximum number of parts that can be created for a single object when using Amazon S3 multipart upload?

- [ ] 3,500 per partitioned prefix
- [x] 10,000
- [ ] There is no limit
- [ ] 5,500

#### Q5. You are presenting information to your team on Amazon S3. What should you put in your presentation on how many tags can be applied per Amazon S3 object?

- [x] 10
> Comments: You can associate up to 10 tags with an object. Tags associated with an object must have unique tag keys.
- [ ] 20
- [ ] 50
- [ ] 5

#### Q6. Which of the following are Amazon S3 managed rules that AWS Config could monitor for Amazon S3? (Select FOUR)

- [ ] Is versioning enabled?
> Comments: Checking that versioning is enabled on all S3 buckets is an S3 managed rule for AWS Config.
- [ ] Are any of the buckets open to the public?
> Comments: Checking for buckets that are open to the public is an S3 managed rule for AWS Config.
- [ ] Is logging enabled on all buckets?
> Comments: Checking that logging is enabled on all S3 buckets is an S3 managed rule for AWS Config.
- [ ] Is replication enabled?
> Comments: Checking for replication rules is an S3 managed rule for AWS Config
- [ ] Are any objects in the Glacier Deep Archive storage class?

#### Q7. As a new storage administrator you are tasked with applying tags to resources. What Amazon S3 resources can tags be applied to?

- [ ] Amazon S3 buckets, prefixes, and objects
- [x] Amazon S3 buckets and objects
> Comments: Amazon S3 tags can be applied to Amazon S3 objects and buckets. With buckets, it's done via Cost Allocation tags.
- [ ] Amazon S3 buckets, prefixes, access points, and objects
- [ ] Amazon S3 objects and access points

#### Q8. Your enterprise uses on-premises SFTP servers for ongoing data collection from third party sources over the internet to a local NAS appliance. You want to transition this workflow to the cloud using the AWS Transfer family. Which AWS services should you consider for backend storage for the ingested data? (Select TWO)

- [x] Amazon EFS
> Comments: “The AWS Transfer Family provides fully managed support for file transfers directly into and out of Amazon S3 or Amazon EFS.”
- [ ] Amazon FSx for NetApp ONTAP
- [ ] Amazon FSX for OpenZFS
- [x] Amazon S3
> Comments: “The AWS Transfer Family provides fully managed support for file transfers directly into and out of Amazon S3 or Amazon EFS.”
- [ ] Amazon EBS, with self-managed NFS servers on Amazon EC2

#### Q9. What is the maximum size of each part in a multipart upload?

- [x] 5GB
> Comments: The maximum size for each part is 5GB. https://docs.aws.amazon.com/AmazonS3/latest/userguide/qfacts.html
- [ ] 5TB
- [ ] 10MB
- [ ] 10GB

#### Q10. You recently enabled cross-region replication as part of your new disaster recovery plan. As part of this effort, you have also enabled Amazon S3 versioning on your bucket as it is a required feature for Amazon S3 replication. You have noticed an unexpected growth in storage consumption and costs associated with your original bucket. What could be driving these increases?

- [x] Lifecycle policies have not been created for the original bucket to expire previous versions of objects.
- [ ] Your replication rule is configured to write objects into the Amazon S3-Standard storage class when replicating objects to your disaster recovery bucket.
- [ ] Amazon S3 replication creates temporary copies of your data before moving that copy of your data to the destination bucket.
- [ ] Existing Amazon S3 Lifecycle policies are disabled when Amazon S3 replication is enabled.

#### Q11. An Amazon S3 bucket has a lifecycle configuration in place and you then configure replication for it. Based on this, which of the following statements is true?

- [ ] The replica of each object will use the same object class as the source object.
- [ ] The lifecycle configuration of the source bucket gets disabled.
- [ ] For cost efficiency, all replicas will use the Glacier Deep Archive object by default.
- [x] The lifecycle configuration of the source bucket is not replicated.
> Comments: "What does Amazon S3 not replicate? Actions performed by lifecycle configuration"

#### Q12. You have been tasked with creating a bucket policy to limit the role "Accounting" to the bucket named "financial" in a prefix of "2021." Which of the following accurately provides the elements associated with the bucket policy to accomplish this requirement?

- [ ] 1
```
Principal = arn:aws:iam:111122223333:/role/accounting
Resource = arn:aws:s3:::financial/
Condition = 2021
```
- [x] 2
```
Principal = arn:aws:iam:111122223333:/role/accounting
Resource = arn:aws:s3:::financial/2021/*
```
> Comments: The element that allows the Accounting role access is the principal keyword. The resource element defines the the bucket and prefix that is allowed as part of the policy
- [ ] 3
```
Role = arn:aws:iam:111122223333:/role/accounting
Resource = arn:aws:s3:::financial/2021/*
```
- [ ] 4
```
Principal = arn:aws:iam:111122223333:/role/financial
Bucket = arn:aws:s3:::financial/2021/*
```

#### Q13. Which Amazon S3 storage classes support object lock?

- [x] All Amazon S3 storage classes, except Amazon S3 Outposts
Comments: Object lock is supported on all Amazon S3 storage classes, except Amazon Outposts
- [ ] All Amazon S3 storage classes
- [ ] All Amazon S3 storage classes, except Amazon S3 Intelligent Tiering
- [ ] All Amazon S3 storage classes, except Amazon S3 Glacier

#### Q14. You have been tasked with documenting the benefits of the Amazon S3 Intelligent Tiering storage class. Which of the following are benefits of the Amazon S3 Intelligent Tiering storage class? (Select TWO)

- [x] Up to 95% cost savings using the optional archive and deep archive tiers.
- [ ] Up to 68% cost savings using the Frequent and Infrequent Access tiers.
- [ ] Opt-in Archive Instant Access tier providing savings of 40% when compared to the Infrequent Access Tier.
- [x] No operational overhead, no lifecycle charges, no retrieval charges, and no minimum storage duration.
- [ ] Discounted lifecycle transition fees when using the optional archive and deep archive tiers.

#### Q15. You have been asked by your team leader to strengthen the security in your environment. You need to audit your Amazon S3 bucket for changes and notify the team lead of any questionable behavior. You also need to make sure that you compare your AWS account to the recommended best practices to make sure that your Amazon S3 bucket permissions do not have open access. Which service should you use to monitor this information?

- [ ] AWS CloudTrail
- [ ] Amazon S3 access logging
- [x] AWS Trusted Advisor
- [ ] AWS CloudWatch

#### Q16. A company has a SQL database and once a day the database is creating a dump which is stored in a single 100+ GB file. For compliance, the company needs to keep the dumps for 365 days. The company moves to Amazon S3 with lifecycle rules to reduce costs. The file's first 1 MB contains a header that includes references to all the tables in the file, which are stored sequentially. In a surprise audit, the system administrator is requested to get a specific table from a dump 85 days ago. What is the most cost-efficient way to get the table? (Select TWO)

- [x] Use S3 Select on the first 1 MB to look at the header and find the location of the table in the file.
Comments: This is the most cost-efficient method to use.
- [ ] Use S3 GET operation first to get the dump file, look at the header, and than use S3 Select to fetch the table in the file.
- [x] Use S3 Select on the first 1 MB to look at the header and find the location of the table in the file. Then, use ranged get to fetch the required table.
Comments: This is correct answer. You first fetch only the 1 MB to get range of the table. and than use select with scanrange to fetch the table. https://docs.aws.amazon.com/AmazonS3/latest/userguide/selecting-content-from-objects.html
- [ ] Use a S3 GET operation to get the dump file and extract the relevant table from the file.
- [ ] Use S3 GET operation first to get the dump file and than use S3 Select to fetch the table in the file.

#### Q17. You have a number of Amazon S3 buckets with access given to both AWS accounts and external accounts. You have been tasked by your management team to ensure that you get findings into the level of public or shared access for each of the Amazon S3 buckets. Which service would you use to complete this task?

- [x] AWS IAM Access Analyzer
- [ ] AWS CloudWatch
- [ ] AWS Config
- [ ] AWS CloudTrail

#### Q18. Which Amazon S3 Intelligent Tiering access tier has the same access characteristics and performance as Amazon S3 Glacier Flexible retrieval?

- [ ] Archive Instant Access
- [ ] Deep Archive Access
- [ ] Frequent Access
- [x] Archive Access

#### Q19. What Amazon S3 feature helps you manage your Amazon S3 storage by creating lists of the objects in a bucket on a defined schedule?

- [ ] Amazon S3 Storage Lens
- [ ] Amazon S3 Server Access Logs
- [x] Inventory Reports
> Comments: Inventory Reports helps you manage your storage by creating lists of the objects in an S3 bucket on a defined schedule. You can configure multiple inventory lists for a bucket.
- [ ] Amazon S3 Storage Class Analysis

#### Q20. You are currently storing all of your object data in the Amazon S3 Standard storage class but would like to benefit from the cost savings provided by transitioning data that is not accessed often to the Amazon S3 Standard Infrequent Access storage class. What AWS tool could you use to identify the most effective lifecycle policy configuration?

- [ ] Amazon QuickSight
- [x] Storage Class Analysis
- [ ] Cost and Usage Reports
- [ ] Amazon S3 Inventory report

#### Q21. What resources can you set Amazon S3 Block Public Access on?

- [ ] S3 buckets, S3 objects and AWS accounts
- [ ] S3 buckets, S3 objects and S3 prefixes
- [x] S3 buckets, access points, and AWS accounts
Comments: Block Public Access can be set on S3 buckets and access point resources as well as at the AWS account level.
- [ ] S3 buckets, S3 objects and access points

#### Q22. You need to document specifications of the Amazon S3 Storage Lens.

How many levels of aggregation does Amazon S3 Storage Lens provide?

- [ ] 4 (Account, Region, Bucket, and Prefix)
- [x] 6 (Organization, Account, Region, Storage Class, Bucket, and Prefix)
> Comments: There are 6 levels of aggregation for S3 Storage Lens (Organization, Account, Region, Storage Class, Bucket, and Prefix).
- [ ] 3 (Account, Region, and Bucket)
- [ ] 5 (Organization, Account, Region, Bucket, and Prefix)

#### Q23. You have been tasked with making sure all new objects in a bucket are minimally encrypted at rest regardless of the options specified when the object is uploaded so not to affect currently running applications. How would you achieve this?

- [ ] Use an access point on the bucket and redirect all application traffic to the access point.
- [ ] Create an AWS Key Management Service (KMS) key and assign permission to the key for application roles and AWS IAM users.
- [x] Enable default encryption for the bucket with at least the sse-s3 option.
> Comments: This will ensure that any new objects put in a bucket will at least get encrypted with the sse-s3 option.
- [ ] Modify your bucket policy with condition statement to deny any puts where the x-amz-server-side-encryption:true header is missing.

#### Q24. You have enabled versioning with MFA Delete on an Amazon S3 bucket. What is required to permanently delete an object version in this bucket? (Select TWO)

- [ ] Amazon S3 Access Point
- [x] Concatenation of your authentication device's serial number, a space, and the authentication code displayed on it
> Comments: "With MFA Delete, two forms of authentication are required to change the versioning state of a bucket or delete an object version: Your AWS account credentials; A valid six-digit code and serial number from an MFA authentication device in your physical possession."
- [ ] Total number of versions of the object
- [x] AWS account credentials
> Comments: "With MFA Delete, two forms of authentication are required to change the versioning state of a bucket or delete an object version: Your AWS account credentials; A valid six-digit code and serial number from an MFA authentication device in your physical possession."
- [ ] Presigned URL

#### Q25. What Amazon S3 feature can be used to simplify data access by creating a unique endpoint with its own access control policies to easily control access to shared datasets in an Amazon S3 bucket?

- [ ] S3 Block Public Access
- [x] S3 Access Points
> Comments: S3 Access Points simplify how you manage data access for your application set to your shared data sets on S3.
- [ ] Access Control Lists (ACLs)
- [ ] Signed URLs

#### Q26. Your team needs to understand more about partitioned prefixes and Amazon S3 buckets. How would you answer this question from the team? How many partitioned prefixes are supported per Amazon S3 bucket?

- [ ] 1,000
- [x] There is no limit
- [ ] 9,000
- [ ] 3,500

#### Q27. Your are presenting to a new project team on Amazon S3 Inventory reports. What should you list in your presentation to answer this question. In which format can you publish Amazon S3 Inventory reports? (Select THREE)

- [ ] XLS
- [x] Parquet
> Comments: The inventory lists are published to CSV, ORC, or Parquet files in a destination bucket.
- [ ] PDF
- [x] ORC
> Comments: The inventory lists are published to CSV, ORC, or Parquet files in a destination bucket.
- [x] CSV
> Comments: The inventory lists are published to CSV, ORC, or Parquet files in a destination bucket.

#### Q28. What are the types of Amazon S3 logging available? (Select TWO)

- [x] Amazon S3 access logs
- [ ] AWS CloudWatch
- [ ] Amazon S3 Storage Lens
- [x] AWS CloudTrail
- [ ] Amazon S3 Inventory

#### Q29. What Amazon S3 feature can be used to limit public access to Amazon S3 resources?

- [x] Amazon S3 Block Public Access
Comments: By default, new buckets, access points, and objects don't allow public access. However, users can modify bucket policies, access point policies, or object permissions to allow public access. S3 Block Public Access settings override these policies and permissions so that you can limit public access to these resources.
- [ ] Amazon S3 Object Lock
- [ ] Amazon S3 Access Control Lists (ACLs)
- [ ] AWS Managed Policies for Amazon S3

#### Q30. Your company is interested in moving to the cloud and wants to use an Amazon S3 to store the data. The data contains sensitive information and you must ensure that the data is protected. Which actions can you take to protect the data when using Amazon S3? (Select TWO)

- [ ] Uploading unencrypted files to Amazon S3 because Amazon S3 encrypts the files by default.
- [ ] Using Secure File Transfer Protocol (SFTP) to connect directly to Amazon S3.
- [x] Using client-side encryption to protect data in transit.
> Comments: Amazon S3 server-side encryption must be enabled on a bucket before uploading objects. Existing objects must be re-uploaded to be encrypted at rest. Server-side encryption does not encrypt data in transit; use client-side encryption instead.
- [ ] Enabling server-side encryption on the Amazon S3 bucket after uploading sensitive data.
- [x] Enabling server-side encryption on the Amazon S3 bucket before uploading sensitive data.
> Comments: Amazon S3 server-side encryption must be enabled on a bucket before uploading objects. Existing objects must be re-uploaded to be encrypted at rest. Server-side encryption does not encrypt data in transit; use client-side encryption instead.

#### Q31. The storage cost of an Amazon S3 bucket has been significantly increasing over the last 12 months. All existing objects are in Amazon S3 Standard storage class and the access pattern to the objects is unknown. You have been tasked with finding a solution to decrease the storage costs with the only requirement that the objects must be immediately available (first byte latency of milliseconds). Which of the following solutions satisfies the requirements in the simplest and most cost effective way?

- [ ] Use Amazon S3 Batch to copy all the existing objects using the same key name and specifying the storage class Amazon S3 Intelligent-Tiering.
- [ ] Create a Amazon S3 Lifecycle policy in the bucket transitioning objects to the Amazon S3 Standard-IA storage class 30 days after creation.
- [ ] Create a Amazon S3 Lifecycle policy in the bucket transitioning objects to the Amazon S3 Standard-IA storage class 30 days after creation and to Amazon S3 Glacier Deep Archive storage class 90 days later.
- [x] Create a Amazon S3 Lifecycle policy in the bucket transitioning objects to the Amazon S3 Intelligent-Tiering storage class 0 days after creation.
> Comments: S3 Intelligent-Tiering is the ideal storage class when the access pattern to the objects is unknown or constantly changing. Using S3 Lifecycle is the easiest way to change the storage class.

#### Q32. How can you identify in which tier within Amazon S3 Intelligent-Tiering that your objects are located? (Select TWO)

- [x] You can make a HEAD request on your objects to report the Amazon S3 Intelligent-Tiering archive access tiers.
- [ ] You can use Amazon S3 analytics – storage class analysis to report the access tier of an object.
- [x] You can use Amazon S3 Inventory to report the access tier of objects.
- [ ] You can use Amazon S3 Object Tags to confirm the access tier of an object.

#### Q33. What capacity costing model does AWS use for block storage services?

- [x] Allocated Capacity
- [ ] Usable Capacity
- [ ] Consumed Capacity
> Comments: Consumed capacity is the amount of data your application has actually written, and may be far less than Allocated capacity. AWS charges for block capacity by allocated Capacity.
- [ ] Formatted Capacity

#### Q34. You have been tasked with examining the various Amazon S3 storage classes and providing a suggestion on which to use. The requirement is for rarely accessed data that needs immediate access in performance-sensitive use cases like image hosting, online file-sharing applications, medical imaging and health records, or news media assets. Based on the requirements, which storage class should you use?

- [ ] Amazon S3 Standard
- [x] Amazon S3 Glacier Instant Retrieval
- [ ] Amazon S3 Standard-IA
- [ ] Amazon S3 Glacier Flexible Retrieval

#### Q35. What AWS service can be used to analyze Amazon S3 server access logs?

- [ ] Amazon Macie
- [x] Amazon Athena
> Comments: Amazon Athena is an interactive query service that makes it easy for you to analyze data directly in Amazon S3, using standard SQL.
- [ ] Amazon S3 Storage Lens
- [ ] Amazon DynamoDB

#### Q36. Which services can you use to analyze data directly in Amazon S3? (Select TWO)

- [x] Amazon Athena
Comments: Amazon Athena is an interactive query service that makes it easy for you to analyze data directly in Amazon S3, using standard SQL.
- [x] Amazon Redshift Spectrum
Comments: Amazon Redshift is a large-scale, managed data warehouse service used with data assets in Amazon S3.
- [ ] Amazon FSx for Lustre
- [ ] AWS Glue

#### Q37. What is maximum number of parts that a multipart object upload can upload to Amazon S3 for a single object?

- [ ] 256
- [ ] 1024
- [ ] Unlimited
- [x] 10,000
> Comments: For a multipart upload, you can upload up to 10,000 parts and each part can be 5GB that will totalize 5TB for a single object. Ref: https://docs.aws.amazon.com/AmazonS3/latest/userguide/qfacts.html

#### Q38. You have configured an Amazon S3 Lifecycle rule to transition all objects contained within a defined prefix from Amazon S3 Standard into the Amazon S3 Standard-IA storage class 30 days after creation. Several months have passed and you notice that a subset of your data did not transition to the Amazon S3 Standard-IA storage class. What could have caused some objects to remain in the Amazon S3 Standard storage class?

- [ ] Your AWS IAM policy providing Amazon S3 Storage Class Analysis access to your entire bucket has been misconfigured.
- [x] Some of your objects are smaller than 128 KB.
- [ ] Some of your objects are larger than the 5 GB limit for a single S3 PUT operation.
- [ ] The proper object tags had not been applied to some of your objects.

#### Q39. What is a prerequisite for Amazon S3 Object Lock?

- [x] Object versioning
> Comments: Object versioning must be enabled on the bucket
- [ ] Encryption
- [ ] Legal Hold

#### Q40. What best describes the performance of Amazon S3 Glacier Instant Retrieval?

- [x] The same throughput performance and latency as Amazon S3 Standard and Amazon S3 Standard-IA.
- [ ] Seconds level retrievals
- [ ] Milliseconds to seconds level
- [ ] 1-5 Minutes

#### Q41. Your management team has asked you to examine the various AWS storage services and look for the service that allows you to pay for the capacity that you consume? Which service has this general pricing model?

- [ ] Amazon Elastic File System (Amazon EFS)
> Comments: With Amazon EFS, you pay for the capacity that you consume.
- [ ] Amazon Elastic Block Store (Amazon EBS)
- [ ] Amazon FSx for Lustre
- [ ] Amazon FSx for Windows File Server

#### Q42. At what level can an Amazon S3 Object Lock be applied?

- [ ] Bucket, Prefix, and Object
- [ ] Bucket, Object, and Access Point
- [x] Bucket, Object, and Object Version
> Comments: Object Locks can be applied at the bucket level, object level, and individual object version level
- [ ] Object, Object Version, and Access Point

#### Q43. You are briefing a new project team member on Amazon S3 features. How would you answer this question from the team. What Amazon S3 feature is used to categorize our objects in Amazon S3?

- [ ] Amazon S3 Storage Class Analysis
- [ ] Amazon S3 Storage Lens
- [x] Amazon S3 Object Tags
> Comments: Use object tagging to categorize Amazon S3 objects.
- [ ] Amazon S3 Intelligent-Tiering

#### Q44. Which of the following are technical considerations when selecting an Amazon S3 storage class? (Select TWO.)

- [ ] Cost of the storage class.
- [x] Latency tolerance of an application or workload.
> Comments: Amazon S3 Standard is designed for performance-sensitive use cases, those that require millisecond access time, and for your most frequently accessed data.
- [ ] Size of your data set.
- [x] Access pattern of the data.
> Comments: Amazon S3 offers you eight different storage classes, allowing you to choose which class of storage best fits your use cases, your data access frequency, and your regulatory compliance requirements
- [ ] Whether the business or the data have compliance or long-term-storage requirements.

#### Q45. Your customer wants to make sure they can meet their Recovery Point Objective (RPO) of 20 minutes with Amazon S3 cross-region replication. What should they implement?

- [ ] Direct all replicas to the Amazon S3 Standard object class.
- [x] Enable Amazon S3 Replication Time Control (RTC).
> Comments: If you need a predictable replication time backed by an SLA, you can enable S3 Replication Time Control (S3 RTC).
- [ ] For source objects that are encrypted, specify that the replicas should not be encrypted.
- [ ] Enable Replica Modification Sync.

#### Q46. What kind of Amazon S3 metrics can you monitor using Amazon CloudWatch? (Select THREE)

- [x] Replication metrics
> Comments: https://docs.aws.amazon.com/AmazonS3/latest/userguide/cloudwatch-monitoring.html
- [x] Amazon Storage Lens Metrics
> Comments: https://docs.aws.amazon.com/AmazonS3/latest/userguide/cloudwatch-monitoring.html
- [x] Request Metrics
> Comments: https://docs.aws.amazon.com/AmazonS3/latest/userguide/cloudwatch-monitoring.html
- [ ] Encryption metrics
- [ ] CloudFront Origin Metrics
