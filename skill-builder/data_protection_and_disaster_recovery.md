## AWS Data Protection and Disaster Recovery

#### Q1. With S3 File Gateway, where do you edit the file share access settings?

- [ ] The file share role policy
- [x] Storage Gateway console
  > Comments: To restrict file access for your clients, you can edit the file share access settings within the Storage Gateway console.
- [ ] The IAM console
- [ ] The appliance console

#### Q2. What are some use cases for AWS Backup? (Select all that apply.)

- [x] Compliance
- [ ] Data center consolidation
- [ ] Migration
- [x] Cloud-centered data-protection

#### Q3. You have enabled versioning with MFA Delete on an Amazon S3 bucket. What is required to permanently delete an object version in this bucket? (Select all that apply.) 

- [ ] Total number of versions of the object
- [x] A valid six-digit code and serial number from the MFA authentication device
> Comments: "With MFA Delete, two forms of authentication are required to change the versioning state of a bucket or delete an object version: Your AWS account credentials; A valid six-digit code and serial number from an MFA authentication device in your physical possession."
- [x] AWS account credentials
> Comments: "With MFA Delete, two forms of authentication are required to change the versioning state of a bucket or delete an object version: Your AWS account credentials; A valid six-digit code and serial number from an MFA authentication device in your physical possession."
- [ ] Presigned URL
- [ ] S3 Access Point

#### Q4. With S3 File Gateway, what is the limit on the number of file shares per gateway?

- [ ] 20
- [ ] 15
- [x] 10
- [ ] 25

#### Q5. What does storage gateway use Challenge-Handshake Authentication Protocol (CHAP) for?

- [ ] A communication protocol used to interconnect network devices on the internet
- [ ] A security protocol for encrypting links between a web server and a browser
- [ ] A third-party service for centrally storing authentication credentials
- [x] An iSCSI protocol that supports authentication between targets and initiators
> Comments: CHAP authentication is an iSCSI protocol that supports authentication between targets and initiators.

#### Q6. A CIO wants to know where backup retention is defined, so they can review the frequency of backups taken by the organization. What would they need to examine?

- [x] Backup Rule within a Backup Plan
- [ ] Backup Config Management
- [ ] Backup Policy Management
- [ ] Backup Vault Retention Policy
- [ ] Backup Assignment within a Backup Plan

#### Q7. As a Storage Administrator, you are working with the Network Engineer to document the ports required for AWS Elastic Disaster Recovery. Which of the following ports are required to replicate your data from your on-premises to AWS? (Select all that apply.)

- [x] Outbound TCP port 443 from your staging/replication area subnet to the AWS Elastic Disaster Recovery endpoint
- [ ] Inbound TCP port 1500 from the Amazon Elastic Compute Cloud (EC2) instance subnet to the source infrastructure
- [ ] Outbound TCP port 80 from your source server to the AWS Elastic Disaster Recovery endpoint
- [x] Outbound TCP port 443 from your source server to the AWS Elastic Disaster Recovery endpoint
- [x] Outbound TCP port 1500 from your source server to the AWS staging/replication area subnet

#### Q8. Your company is exploring moving to the cloud and have asked you to examine the various storage offerings. You need to be able to analyze the various offerings and compare to your on-premise storage infrastructure. Which of the following is not considered a barrier to Operational Agility when using on-premises storage infrastructures?

- [ ] The amount of time to procure and install new storage systems or capacity.
> Comments: Even after approval, it can take weeks or months to order, receive, and install new systems or additional capacity for existing ones. Many organizations offer provision storage capacity to deal with implementation and budgeting delays. The unused capacity consumes space and costly resources while waiting to be used.
- [ ] The inability to reduce capacity as needs change.
- [x] The complexity of on-premise storage.
> Comments: Organizations using Legacy Storage on-premise already have training and procedures in place for even the most complex storage tasks.
- [ ] The resources, time and processes required to make changes in the storage infrastructure.

#### Q9. What are the key reasons to use AWS Backup over service-native data protection? (Select all that apply.)

- [x] Compliance and regulatory audit and report capabilities
- [ ] Replication capabilities
- [x] Support for multiple AWS services
- [x] Built in orchestration and centralized management
- [ ] Performance for backup and restore

#### Q10. A CIO wants to know where AWS Backup saves her organization's recovery points. Where are these recovery points saved?

- [x] An AWS Backup vault
- [ ] A Recovery Point vault
- [ ] The organization's EFS filesystem
- [ ] A Backup bucket

#### Q11. Your enterprise has issued a mandate that all new Amazon EBS volumes created within your AWS account should have a tag with the key "CostCenter". Which strategy would you recommend for enforcing this?

- [ ] Train your cloud storage administrators to use the "Tag on Creation" feature when creating new volumes
> Comments: Works, but cannot be enforced
- [ ] Implement a Lambda function that runs every five minutes, and deletes any EBS volume in the account that does not have the required tag
- [ ] Deny the "CreateVolume" action for all IAM users and roles in the account except for one dedicated storage administrator, who takes charge of managing all EBS-related requests
- [x] For all IAM policies that allow the "CreateVolume" action, add a condition requiring the tag "CostCenter" with a value to be a part of the request

#### Q12. Which of the following statements about the root volume of an Amazon EC2 instance are correct? (Select all that apply.)

- [ ] A root Amazon EBS volume is retained by default, when the instance terminates.
- [x] For Windows instances, the root volume must be an Amazon EBS volume.
> Comments: For Windows instances, the root volume must be an Amazon EBS volume; instance store is not supported for the root volume due to the temporary nature of the instance store.
- [ ] A Windows instance can have only one instance store volume, which must be the root volume.
- [x] It is a best practice to separate the root volume from your user data volumes.
> Comments: It is a best practice to separate the root volume from your data volumes so that each can be detached and reattached without them interfering with each other.
- [ ] For Linux instances, the root volume must be an Amazon EBS volume.

#### Q13. When does a service-native solution data protection option work the best? (Select all that apply.)

- [ ] When you want to manage your backup through the centralized AWS Backup.
- [x] When there are no auditing requirements.
Comments: Service-native solutions work the best when you have no auditing requirements for the service and are only required to back up a limited number of AWS services.
- [x] When you have to back up only a limited number of AWS services.
Comments: Service-native solutions work the best when you have no auditing requirements for the service and are only required to back up a limited number of AWS services.
- [ ] When you need the additional options of disaster-recovery solutions.
- [ ] When you want to create, automate, and simplify administration of all backups in your environment.

#### Q14. Which metrics would you use to understand throughput between your S3 File Gateway and the AWS Cloud? (Select all that apply.)

- [x] CloudBytesDownloaded
> Comments: Analyze the CloudBytesDownloaded and CloudBytesUploaded metrics to understand throughput between your S3 File Gateway and the AWS Cloud.
- [ ] ReadBytes
- [ ] WriteBytes
- [ ] IOWaitPercent
- [x] CloudBytesUploaded
> Comments: Analyze the CloudBytesDownloaded and CloudBytesUploaded metrics to understand throughput between your S3 File Gateway and the AWS Cloud.

#### Q15. Which statement, if true, would make 'stored volume' the appropriate choice for your Storage Gateway Volume Gateway?

- [ ] Your volume gateway must be hosted on an Amazon EC2 instance.
- [ ] Only a small quantity of your data is active at any given time.
- [x] You need all of your data stored locally and only require Amazon Elastic Block Store (Amazon EBS) snapshots for backup.
> Comments: Stored volume is best suited for when you need all your data stored locally and only require Amazon EBS snapshots for backup and recovery purposes.
- [ ] Only your most active data must be stored locally for low-latency access.

#### Q16. As the DR Manager of your organization, you want to make sure to follow best practices for recovery using AWS Elastic Disaster Recovery. What would you do to ensure this? (Select all that apply.)

- [x] If you choose to failback, start replicating your data back to your original source environment as soon as it is back online in order to shorten failback time
- [ ] When replicating back to your source, always replicate back to the original servers
- [ ] When you are facing a large scale disaster event, it is advised to recover one server at a time using AWS Elastic Disaster Recovery
- [x] After you have failed over to AWS, evaluate whether to continue operating your workload as primary on AWS or whether to fail back to your original source

#### Q17. What Amazon S3 feature can be used to limit public access to Amazon S3 resources?

- [ ] AWS Managed Policies for S3
- [x] S3 Block Public Access
> Comments: By default, new buckets, access points, and objects don't allow public access. However, users can modify bucket policies, access point policies, or object permissions to allow public access. S3 Block Public Access settings override these policies and permissions so that you can limit public access to these resources.
- [ ] S3 Access Control Lists (ACLs)
- [ ] S3 Object Lock

#### Q18. Which setting is required to activate an AWS Storage Gateway before you can deploy it?

- [ ] Availability Zone
- [ ] AWS Region
> Comments: The Storage Gateway is deployed to a selected AWS Region. This setting is required to deploy the service.
- [ ] Volume group
- [ ] Security group

#### Q19. Which FSx for Windows File Server deployment type takes advantage of cost-optimized hard disk drive (HDD) storage and offers cost optimization for your Amazon FSx File Gateway deployment?

- [ ] Single-AZ 1
- [ ] Multi-AZ
- [x] Singe-AZ 2
> Comments: Single-AZ 2 is the latest Single-AZ for the FSx for Windows deployment type and can take advantage of cost-optimized HDD storage.
- [ ] Local zone

#### Q20. Which statement is true in regard to the Amazon FSx for Windows File Server file system that you attach to your Amazon FSx File Gateway?

- [x] The Amazon FSx file system that you attach must be part of the same AWS account and AWS Region as the FSx File Gateway.
- [ ] The Amazon FSx file system that you attach must be in the same VPC as the Active Directory Domain Controller.
- [ ] The FSx for Windows File Server must be in the same AWS Region as the FSx File Gateway but can be owned by a different AWS account.
- [ ] An FSx for Windows File Server does not need to be attached to the FSx File Gateway.

#### Q21. Which Amazon S3 storage classes support object versioning?

- [ ] All Amazon S3 storage classes, except Amazon S3 Outposts
> Comments: Object versioning is supported on all Amazon S3 storage classes, except Amazon Outposts
- [ ] All Amazon S3 storage classes, except Amazon S3 Glacier Deep Archive
- [ ] All Amazon S3 storage classes, except Amazon S3 Intelligent Tiering
- [ ] All Amazon S3 storage classes except Amazon S3 Glacier

#### Q22. Which setting is required to activate the AWS Storage Gateway before you can deploy it?

- [ ] An Availability Zone
- [ ] A security group
- [ ] AWS Region
> Comments: Your Storage Gateway is deployed to a specific Region.
- [ ] A virtual private cloud (VPC)

#### Q23. What are the Tape Gateway status types that reflect archived tape health? (Select all that apply.)

- [x] ARCHIVED
> Comments: Each archived tape has an associated status which reflects its health. Those statuses include: ARCHIVED, RETRIEVING, and RETRIEVED.
- [x] RETRIEVED
> Comments: Each archived tape has an associated status which reflects its health. Those statuses include: ARCHIVED, RETRIEVING, and RETRIEVED.
- [ ] AVAILABLE
- [ ] CREATED
- [x] RETRIEVING
> Comments: Each archived tape has an associated status which reflects its health. Those statuses include: ARCHIVED, RETRIEVING, and RETRIEVED.

#### Q24. As an IT manager in your organization, you are writing an internal disaster recovery runbook for day to day operation and recovery. What should be your schedule for planned DR drills?

- [ ] Drills will be launched just before a disaster occurs in my source environment
- [ ] Generally, there is no need to drill the DR implementation
- [x] We should maintain recovery readiness, monitoring our AWS Elastic Disaster Recovery implementation on a regular basis and conduct periodic drills as per my company policy

#### Q25. A solutions architect would recommend AWS Backup for which common customer use cases? (Select all that apply.)

- [ ] Archive
- [ ] VTL target for on-premises backup
- [ ] Migration tool
- [x] Hybrid data protection
- [x] Cloud-native backup

#### Q26. If you wish to store your on-premise application data in S3 for durability, while only keeping the most recently active data on-premises, which of the following Volume Gateway modes would you use?

- [x] Cached
> Comments: Volume Gateway, cached mode, allows you to store your data in Amazon Simple Storage Service (Amazon S3) and retain a copy of frequently accessed data subsets locally.
- [ ] Stored
- [ ] Storage
- [ ] Storage

#### Q27. Which AWS service assists you in capturing events for Amazon FSx File Gateway to monitor what request was made, the IP address from which the request was made, who made the request, and when it was made?

- [x] AWS CloudTrail
Comments: CloudTrail assists you in capturing events for FSx File Gateway to monitor what request was made, the IP address from which the request was made, who made the request, and when it was made.
- [ ] Amazon CloudWatch
- [ ] AWS Direct Connect
- [ ] AWS Site-to-Site VPN

#### Q28. Deployment of a Tape Gateway with AWS has four steps: Set up the gateway, connect to AWS, activate the gateway, and configure gateway. Which step do you manage settings for the cache and upload buffer?

- [ ] Step 1: Set up the gateway
- [ ] Step 3: Review and activate
- [ ] Step 2: Connect to AWS
- [x] Step 4: Configure gateway

#### Q29. What Amazon S3 feature can be used to simplify data access by creating a unique endpoint with its own access control policies to easily control access to shared datasets in an Amazon S3 bucket?

- [ ] S3 Block Public Access
- [ ] Signed URLs
- [ ] Access Control Lists (ACLs)
- [x] S3 Access Points
> Comments: S3 Access Points simplify how you manage data access for your application set to your shared data sets on S3.

#### Q30. A backup administrator wants to "fan out" copies of their backups from a central backup account to individual accounts in the event the central backup account is compromised. Which AWS service should they use to enable cross-account management and backup?

- [ ] Backup Vault Lock
- [x] AWS Organizations
- [ ] Backup Vault
- [ ] AWS Backup Audit Manager
- [ ] AWS Config

#### Q31. As a Business Manager you need to understand the benefits of using AWS in your backup operations. Which of these are advantages of using AWS ? (Select all that apply)

- [x] Reduce variable costs
- [x] Global secure infrastructure
- [ ] Increased TCO
- [ ] Modify existing workflows
- [ ] Complicated pricing model

#### Q32. A customer asks a solutions architect which AWS service categories are supported by AWS Backup. Which services are included? (Select all that apply.)

- [x] Compute
- [ ] Infrastructure As Code (IaC)
- [x] Object storage
- [x] Block storage
- [ ] Secrets and Key Management

#### Q33. With The Amazon S3 File Gateway, what is the default bandwidth rate limit for an activated gateway?

- [ ] 1GB
- [x] No default rate limit
- [ ] 12 MB
- [ ] 12 GB

#### Q34. When creating a new tape with Tape Gateway, you set the tape pool storage class option for archive purposes. Which of the following options would work best if your company actively uses archived data and needs access to them on a frequent basis?

- [ ] Use the block (Volume) storage option instead of archives
- [ ] S3 Storage Buckets
- [x] S3 Glacier Flexible Retrieval
> Comments: S3 Glacier Flexible Retrieval is used for more active archives where you can retrieve tapes typically within 3-5 hours. S3 Glacier Deep Archive is for long-term data retention and digital preservation where data is access once or twice a year.
- [ ] S3 Glacier Deep Archive

#### Q35. With Tape Gateway, what feature of virtual tapes with AWS helps ensure that the data on active tapes in your virtual tape library (VTL) cannot be overwritten or erased?

- [ ] IAM permissions
- [x] WORM protection
> Comments: WORM-enabled virtual tapes help ensure that the data on active tapes in your virtual tape library (VTL) cannot be overwritten or erased. WORM configuration can only be set when tapes are created.
- [ ] SSL/TLS encryption
- [ ] Security group permissions

#### Q36. How many 9s of durability does Amazon S3 provide for Tape Gateway virtual tapes?

- [x] 11
> Comments: Amazon S3 provides 11 9s of durability for your virtual tapes.
- [ ] 10
- [ ] 13
- [ ] 9

#### Q37. What are the options for locking a backup vault with AWS Backup Vault Lock? (Select all that apply.)

- [x] AWS Backup SDK
- [ ] Amazon SNS
- [ ] Amazon SES
- [x] AWS Backup CLI
- [x] AWS Backup API

#### Q38. A compliance officer at your organization asks you where AWS Backup Audit Manager delivers daily reports. Where would these reports be located?

- [ ] To an EFS file system you designate
- [ ] To the management account of your AWS Organizations
- [ ] To an EC2 instance you designate
- [x] To an S3 bucket you designate

#### Q39. As a Business Manager you need to understand the existing native backup features available in AWS. Which of these are native AWS Backup features (Select all that apply)

- [ ] Database backups on EC2
- [x] Amazon EBS snapshots
- [x] Amazon DynamoDB backups
- [ ] GitHub backups
- [x] Amazon RDS snapshots

#### Q40. A customer asks which AWS services are supported by AWS Backup. Which services are included? (Select all that apply)

- [x] Amazon S3
- [ ] Amazon Kinesis
- [ ] AWS KMS
- [x] Amazon RDS
- [x] Amazon EC2

#### Q41. A solutions architect is describing the major AWS Data Protection offerings to a customer. Which offerings should be included? (Select all that apply.)

- [ ] Real-time analysis of video and data streams
- [x] Service-native backups and snapshots
- [x] AWS Elastic disaster recovery
- [ ] Custom Scripts developed by individuals
- [x] Centralized policy based backups and snapshots

#### Q42. As a Business Manager you need to understand the benefits of the Native Backup features provided by AWS. Which of these features are native to AWS? (Select all that apply.)

- [ ] Wasted Capacity
- [x] Pay As you Use Model
- [x] No Capacity Planning
- [x] No Capital Investment
- [ ] Continuous planning for Storage Capacity

#### Q43. You want to set an alarm to alert you when there is a high IO wait on an activated gateway. Which tool should you use to create this type of alarm?

- [ ] AWS CloudTrail
- [ ] Amazon CloudWatch
> Comments: Using CloudWatch, you can set alarms to notify you of changes in workloads. Alarms can be based on a single metric or a combination of metrics.
- [ ] AWS Config
- [ ] AWS Cloudfront

#### Q44. A Database Administrator is reading documentation about whether to turn on AWS Backup management of DynamoDB backups. What are the advanced features that become available when they turn on this service? (Select all that apply.)

- [ ] Export backups to Amazon S3 Buckets
- [x] Cost allocation tagging
- [ ] Cost savings
- [x] Business continuity using Cross region and cross account backups
- [ ] Security

#### Q45. A backup administrator wants to share their data across their AWS environment. What are the ways they can do so? (Select all that apply.)

- [x] Cross-region
- [x] Cross-account
- [ ] Synchronous
- [ ] Asynchronous
- [ ] Hybrid (On-premises to the Cloud)

#### Q46. A Systems Administrator asks when to use an AWS service-native data protection option instead of AWS Backup. When is it appropriate to use one of these options? (Select select all that apply.)

- [ ] When you want to manage your backup through the centralized AWS Backup.
- [x] When you are not subject to audit requirements.
- [x] When you have to back up only a limited number of AWS services.
- [ ] When you want to create, automate, and simplify administration of all backups in your environment.
- [ ] When you need the additional options of disaster-recovery solutions.

#### Q47. As a business user, you want to secure your ability to recover in other Regions if a source Region is wiped out. What are the requirements of setting up Cross Region Copies in AWS Backup? (Select all that apply.)

- [ ] Administrative privileges in the destination region
- [x] Build policies around a multiple-Region scheme
- [x] Credentials to setup Vault in Destination Region
- [ ] Setting up VPN Connection between regions

#### Q48. How many backup vaults can you have per AWS Region?

- [ ] 500
- [ ] Unlimited
- [ ] 1000
- [x] 100
> Comments: You can create 100 backup vaults per AWS region.

#### Q49. What are the hybrid cloud workloads supported by AWS Backup? (Select all that apply.)

- [ ] On-premises NAS
- [x] VMware
- [ ] On-premises Database
- [x] AWS Storage Gateway
- [ ] Amazon S3

#### Q50. An auditor working for a data protection regulatory body wants to know whether or not your backups are encrypted. Which control in AWS Backup Audit Manager proves that they are?

- [ ] Backup plan minimum frequency, and minimum retention control
- [ ] Backup recovery point minimum retention encryption
- [ ] Backup resources protected by backup plan control
- [ ] Backup prevent recovery point manual deletion control
- [x] Backup recovery point encrypted control