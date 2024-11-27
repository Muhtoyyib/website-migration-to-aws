# Technical Documentation : Migration of Blrighthomes.com to AWS
<hr />

Project Title: Migrating blrighthomes.com to AWS

Client: Blrighthomes

Revision Date: 2024-11-27

<hr />


## Table of Contents

* [Introduction](#Introduction) 
* [Project Objectives](#Objectives)
* [Deliverables](#Deliverables)
* [Architecture](#Architecture)
* [AWS Services Utilized](#AWS-Services-Utilized)
* [Migration Phases](#Migration-Phases)
* [Cost Analysis](#Cost-analysis)
* [Potential Challenges and Mitigations](#Potential-Challenges-and-Mitigations)
* [Success Criteria](#Success-Criteria)
* [Communication Plan)(#Communication-Plan)
* [APPENDIX](#APPENDIX)

<hr />

## Introduction

This documentation outlines the migration process for blrighthomes.com from its current hosting provider, Hostinger, to Amazon Web Services (AWS). The objective is to leverage AWS's robust infrastructure for improved scalability, security, and website performance.

## Objectives

- Migrate blrighthomes.com, a static portfolio/landing website, from Hostinger to AWS.
- Utilize a serverless architecture for cost-effectiveness and scalability.
- Implement AWS services like S3, CloudFront, Route 53, and CloudWatch for hosting, content delivery, domain management, and monitoring.
- Enhance website security with features like HTTPS.
- Improve website performance through content delivery network (CDN) and caching strategies.

## Deliverables

- Fully functional blrighthomes.com website hosted on AWS S3 with CloudFront distribution.
- Domain name (blrighthomes.com) transferred and managed via AWS Route 53.
- AWS infrastructure diagram depicting the migration setup.
- Comprehensive documentation outlining the migration process and configuration details.
- Monitoring and logging established with AWS CloudWatch for website health and performance tracking.

<hr />

## Architecture

### **Before Migration**: 

![Cloud Architecture Page 1](https://github.com/user-attachments/assets/9ecf4d9c-9568-4cca-8ddd-57b3405669d3)


### **After Migration**:

![Cloud Architecture Page 1 (1)](https://github.com/user-attachments/assets/4b2b2592-e6db-4a68-adb4-85d587103d1f)

**Components**

Route 53: DNS management and domain registration.
CloudFront: Content Delivery Network (CDN) for reduced latency.
S3: Storage for static website hosting
CloudWatch: Monitoring for performance metrics, logs, and alerts.

<hr />

## AWS Services Utilized

The migration will leverage the following AWS services to achieve the project objectives:

1. **Amazon S3 (Simple Storage Service):** A scalable object storage service for hosting static website content (HTML, CSS, JavaScript, images) with high availability and durability.
2. **Amazon CloudFront:** A global content delivery network (CDN) that caches website content at geographically distributed edge locations, reducing latency and improving website loading speed for users worldwide.
3. **Amazon Route 53:** A highly available and scalable Domain Name System (DNS) service for managing domain name registration, routing traffic to the migrated website on AWS S3 via CloudFront.
4. **Amazon CloudWatch:** A monitoring service for collecting and visualizing real-time metrics on website performance, resource utilization, and application health on AWS.

<hr />

## Migration Phases

The migration process will be executed in distinct phases:

### **Phase 1: Planning and Preparation (Day 1)**

- Activities: Gather website requirements, define migration strategy, configure AWS account and security credentials.
- Deliverables: Detailed migration plan, documented security procedures.

### **Phase 2: Website Migration (Day 2)**

- Activities: Migrate website files (HTML, CSS, JavaScript, images) to an S3 bucket with appropriate access controls.
- Deliverables: Website content successfully uploaded to S3 bucket.

### **Phase 3: CloudFront Distribution Setup (Day 3)**

- Activities: Create a CloudFront distribution pointing to the S3 bucket origin, configure caching behavior and security settings (HTTPS).
- Deliverables: Operational CloudFront distribution serving website content from the S3 bucket.

### **Phase 4: Domain Name Transfer and Routing (Day 4-5)**

- Activities: Transfer domain name (blrighthomes.com) to AWS Route 53 and configure an alias record pointing to the CloudFront distribution.
- Deliverables: Domain name successfully transferred and DNS records updated for website routing through CloudFront.

### **Phase 5: Testing and Validation (Day 5)**

- Activities: Perform comprehensive testing of website functionality, performance, and security on the migrated platform.
- Deliverables: Verified website operation and successful migration to AWS.

### **Phase 6: Monitoring and Optimization (Day 6)**

- Activities: Implement CloudWatch for website monitoring, analyze performance metrics, and identify potential optimizations.
- Deliverables: Established website monitoring with CloudWatch for ongoing health and performance tracking.

<hr />


## Cost analysis

Below is the cost analysis generated using the **aAWS Pricing Calculator** 


![monthly estimate](https://github.com/user-attachments/assets/7a6a4980-8510-4651-8517-1a64a8eeccfa)


![Yearly estimate](https://github.com/user-attachments/assets/f9d960b1-5882-4a4c-8f03-5471ebd0b59f)




## Potential Challenges and Mitigations

The migration process might encounter some challenges, but we have mitigation strategies in place:

 
**Challenge:** Difficulty acquiring website files using migration tools.
**Mitigation:** Collaborate with the client to obtain the complete website file set directly.

 
**Challenge:** Unexpected website functionality issues after migration.
**Mitigation:** Implement rollback procedures to revert to the previous hosting provider if critical issues arise. Perform thorough testing throughout the migration process to minimize this risk.

**Challenge:** Security misconfigurations during AWS setup.
**Mitigation:** Follow AWS security best practices and conduct rigorous security testing before launching the migrated website.


## Success Criteria

- Seamless access to blrighthomes.com website through CloudFront with HTTPS enabled.
- Verified DNS resolution via Route 53 alias record pointing to the CloudFront distribution.
- Measurable improvement in website loading speed and reduced latency for global users.
- Error-free functionality across all website pages and features.
  

## Communication Plan


- **Kick-off Meeting:** An initial meeting to establish project goals, timelines, and communication channels.
- **Regular Status Updates:** Weekly status updates via email or project management tools to keep the client informed about project progress.
- **Issue Tracking:** Use a project management tool to track and prioritize issues and tasks.
- **Escalation Procedures:** Define clear escalation procedures for critical issues or delays.
- **Post-Migration Review:** Conduct a post-migration review to assess the overall success of the project and identify any lessons learned.

<hr />

## APPENDIX

### Technical Process

**1. Setup S3 Bucket and Static Website Hosting***

- Log in to the AWS Management Console.  
- Create an S3 bucket with the same name as your domain.  
- Enable static website hosting and configure index and error documents (e.g., index.html, 404.html)

Upload your website files to the bucket. Use the console or CLI for bulk uploads.  
- Configure bucket policy to restrict public access but allow CloudFront access​.

[AWS Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started-cloudfront-overview.html) [AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/website-hosting-custom-domain-walkthrough.html)


**2. Configure Cloudfront Distribution***

- Open the CloudFront console and create a new distribution.  
- Set the S3 bucket as the origin and create an Origin Access Control (OAC).  
- Configure Viewer Protocol Policy to redirect HTTP to HTTPS​ [AWS Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started-cloudfront-overview.html). Enable caching and set default cache behavior settings.  
- Choose "Custom SSL Certificate" to use HTTPS (CloudFront automatically provides SSL if ACM certificate is linked).


**3. Setup Route53 for Domain Mapping**

- Open Route 53 and create a hosted zone for your domain.  
- Add alias records pointing to the CloudFront distribution (not the S3 bucket).  
- Test DNS resolution using dig or nslookup​

[AWS Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started-cloudfront-overview.html) [AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/website-hosting-custom-domain-walkthrough.html)

  

**4. Enable Monitoring and Logging**

- Enable CloudFront and S3 logging by creating a logging bucket.  
- Configure CloudWatch for monitoring key metrics like latency and errors.  
- Optionally, configure alerts for specific thresholds​

[AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/website-hosting-custom-domain-walkthrough.html)

  

**5 Test and Optimize Deployment**

- Test the website by accessing the CloudFront domain and verify caching and HTTPS.  
- Optimize caching by setting longer TTLs for static content.  
- Validate bucket versioning and backups​

[AWS Documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started-cloudfront-overview.html)


### Architecture Description

The architecture includes the following:
  
1. **S3 Bucket** Stores static website content.
2. **CloudFront:** Serves content globally, provides HTTPS, and handles caching.
3. **Route 53:** Manages DNS and maps your domain to the CloudFront distribution.
4. **AWS CloudWatch:** Monitors performance and provides logs.
5 **Versioning and Access Control:** Ensures content integrity and restricts public access directly to the S3 bucket.
   
   
#### Key Notes and Best Practices

- **Domain as Bucket Name:** Use your exact domain name as the S3 bucket name for seamless integration.
- **Access Control:** Restrict public access to the S3 bucket by using Origin Access Identity (OAI) for CloudFront.
- **Bucket Versioning:** Enable versioning on the S3 bucket to manage content updates.
- **Caching:** Leverage CloudFront caching to reduce latency and transfer costs.
- **HTTPS and Security:** Use CloudFront's SSL capabilities for secure content delivery.

https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html










