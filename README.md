# Migrating blrighthomes.com to AWS

This document outlines the migration process for blrighthomes.com from its current hosting provider, Hostinger, to Amazon Web Services (AWS). The objective is to leverage AWS's robust infrastructure for improved scalability, security, and website performance.

## Project Overview
   
blrighthomes.com is a static portfolio/landing website. Currently hosted on Hostinger, this project aims to migrate the website and its domain name to AWS for a more secure and cost-effective solution.

Here's a breakdown of the existing and new setup:

**Existing (Hostinger)**: Shared hosting environment (likely) with limited scalability and security features.
**New (AWS)**: Serverless architecture utilizing S3 for static website hosting, CloudFront for content delivery, Route 53 for domain management, and CloudWatch for monitoring. This approach offers greater scalability, enhanced security, and improved performance.

## Target Architecture
   
Before Migration:

Hostinger: (Insert a simple diagram representing shared hosting, database storage if applicable)

After Migration:

AWS: (Insert a diagram showcasing S3 bucket, CloudFront distribution, Route 53 integration, and any other relevant AWS services)

## AWS Services Utilized

- **Amazon S3**: Secure, scalable object storage for hosting static website content (HTML, CSS, JavaScript, images).
- **AWS CloudFront**: Content Delivery Network (CDN) service to improve website loading times for global users by caching content at edge locations.
- **AWS Route 53**: Managed Domain Name System (DNS) service for managing AtrMotors.com domain name and routing traffic to the website hosted on S3 via CloudFront.
- **AWS CloudWatch**: Monitoring and logging service to track website health, performance metrics, and identify potential issues.
- **AWS Identity and Access Management (IAM): Service for creating users and roles with specific permissions to access AWS resources securely.
  
## Migration Phases

The migration process will be divided into distinct phases:

**Phase 1**: Planning and Prerequisites

Verify domain ownership and initiate transfer process to AWS Route 53.
Create IAM roles and users with appropriate access for migration tasks.
Set up initial infrastructure in the AWS account (e.g., S3 bucket).

Phase 2: S3 Bucket Setup and File Migration

Configure an S3 bucket for static website hosting.
Migrate website files (HTML, CSS, JavaScript, images) from Hostinger to the S3 bucket.
Set appropriate access permissions for the S3 bucket.
Phase 3: CloudFront Distribution Configuration

Create a CloudFront distribution pointing to the S3 bucket hosting the website.
Configure caching behavior, security settings (HTTPS), and Origin Access Identity (OAI) for secure communication between CloudFront and S3.
Phase 4: Route 53 DNS Setup and Testing

Configure a hosted zone in Route 53 for AtrMotors.com domain.
Create an alias record in Route 53 pointing the domain to the CloudFront distribution.
Perform thorough testing to ensure website accessibility through the new domain.
Phase 5: Monitoring, Optimization, and Final Switchover

Monitor website performance using CloudWatch after switching traffic to the new AWS setup.
Optimize CloudFront caching and other configurations for improved user experience.
Once testing is complete, finalize the migration by switching traffic from Hostinger to AWS.
5. Possible Challenges and Solutions
Challenge: DNS propagation delays can cause temporary disruptions during domain transfer.

Solution: Schedule the migration for a low-traffic window and adjust DNS Time-To-Live (TTL) values for faster propagation.

Challenge: Incorrect S3 or CloudFront configuration can lead to website access issues.

Solution: Extensive testing using AWS CloudFront test URLs before switching traffic. Utilize the AWS documentation and support resources for troubleshooting.

Challenge: Downtime during migration is a potential risk.

Solution: Perform a staged migration process with testing in a development environment before switching traffic to the production environment on AWS.

6. Rollback Plan
Maintain a backup of the website files and database (if applicable) on Hostinger during the migration period.
Document each migration phase in detail to facilitate a rollback if necessary.
Utilize Route 53 to quickly switch back to Hostinger's DNS if critical issues arise on AWS.
7. Success Criteria
Seamless access to AtrMotors.com website through CloudFront with HTTPS enabled.
Verified DNS resolution via Route 53 alias record pointing to the CloudFront distribution.
Enhanced website loading speed and reduced latency for global users.
Error-free functionality across all website
