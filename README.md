# Technical Documentation : Migration of Blrighthomes.com to AWS
<hr />

Project Title: Migrating blrighthomes.com to AWS

Client: Blrighthomes

Revision Date: 2024-11-27

<hr />


## Table of Contents

* [Introduction](#Architecture)
* Project Objectives
* Deliverables
* AWS Services Utilized
* Migration Phases
* Potential Challenges and Mitigations
* Cost Analysis

## Introduction

This Statement of Work (SOW) outlines the migration process for blrighthomes.com from its current hosting provider, Hostinger, to Amazon Web Services (AWS). The objective is to leverage AWS's robust infrastructure for improved scalability, security, and website performance.

## Project Objectives

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


<a name="headers"/>
## Architecture

**Before Migration**: 

![Cloud Architecture Page 1](https://github.com/user-attachments/assets/9ecf4d9c-9568-4cca-8ddd-57b3405669d3)



**After Migration**:

![Cloud Architecture Page 1 (1)](https://github.com/user-attachments/assets/4b2b2592-e6db-4a68-adb4-85d587103d1f)


## AWS Services Utilized

The migration will leverage the following AWS services to achieve the project objectives:

1. **Amazon S3 (Simple Storage Service):** A scalable object storage service for hosting static website content (HTML, CSS, JavaScript, images) with high availability and durability.
2. **Amazon CloudFront:** A global content delivery network (CDN) that caches website content at geographically distributed edge locations, reducing latency and improving website loading speed for users worldwide.
3. **Amazon Route 53:** A highly available and scalable Domain Name System (DNS) service for managing domain name registration, routing traffic to the migrated website on AWS S3 via CloudFront.
4. **Amazon CloudWatch:** A monitoring service for collecting and visualizing real-time metrics on website performance, resource utilization, and application health on AWS.

## Migration Phases

The migration process will be executed in distinct phases:

**Phase 1: Planning and Preparation**

* **Activities:** Gather website requirements, define migration strategy, configure AWS account and security credentials.
* **Deliverables:** Detailed migration plan, documented security procedures.

**Phase 2: Website Migration**

* **Activities:** Migrate website files (HTML, CSS, JavaScript, images) to an S3 bucket with appropriate access controls.
* **Deliverables:** Website content successfully uploaded to S3 bucket.

**Phase 3: CloudFront Distribution Setup**

* **Activities:** Create a CloudFront distribution pointing to the S3 bucket origin, configure caching behavior and security settings (HTTPS).
* **Deliverables:** Operational CloudFront distribution serving website content from the S3 bucket.

**Phase 4: Domain Name Transfer and Routing**

* **Activities:** Transfer domain name (blrighthomes.com) to AWS Route 53 and configure an alias record pointing to the CloudFront distribution.
* **Deliverables:** Domain name successfully transferred and DNS records updated for website routing through CloudFront.

**Phase 5: Testing and Validation**

* **Activities:** Perform comprehensive testing of website functionality, performance, and security on the migrated platform.
* **Deliverables:** Verified website operation and successful migration to AWS.

**Phase 6: Monitoring and Optimization**

* **Activities:** Implement CloudWatch for website monitoring, analyze performance metrics, and identify potential optimizations.
* **Deliverables:** Established website monitoring with CloudWatch for ongoing health and performance tracking.


## Cost analysis



## Potential Challenges and Mitigations

The migration process might encounter some challenges, but we have mitigation strategies in place:

**Challenge:** Difficulty acquiring website files using migration tools.
**Mitigation:** Collaborate with the client to obtain the complete website file set directly.

**Challenge:** Unexpected website functionality issues after migration.
**Mitigation:** Implement rollback procedures to revert to the previous hosting provider if critical issues arise. Perform thorough testing throughout the migration process to minimize this risk.

**Challenge:** Security misconfigurations during AWS setup.
**Mitigation:** Follow AWS security best practices and conduct rigorous security testing before launching the migrated website.

This document provides a comprehensive overview of the Blrighthomes.com migration to AWS. By following this plan and addressing potential challenges effectively, we can ensure a seamless transition and achieve the desired website performance and security on the AWS platform.


## Success Criteria

- Seamless access to blrighthomes.com website through CloudFront with HTTPS enabled.
- Verified DNS resolution via Route 53 alias record pointing to the CloudFront distribution.
- Measurable improvement in website loading speed and reduced latency for global users.
- Error-free functionality across all website pages and features.










