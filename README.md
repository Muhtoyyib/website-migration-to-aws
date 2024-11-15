# Migrating AtrMotors.com to AWS S3

## Project Overview

This project aims to migrate a client's website -  static portfolio/landing website - from Hostinger to Amazon Web Services (AWS). The project aims to create a more secure and cost-effective solution by leveraging AWS's robust and scalable infrastructure. The website, being static, does not require a traditional server. Therefore, the project will utilize Amazon S3 for static website hosting, Amazon Route 53 for domain name management, GitHub Actions for continuous integration and continuous delivery (CI/CD), and AWS CloudWatch to monitor website performance. This approach will ensure a reliable and efficient deployment process.

## Objectives

- Successfully migrate client's website to AWS.
- Successfully migrate client's domain name to AWS.
- Implement CI/CD  for automated website deployments.
- Ensure website performance and scalability.


## Scope

- Migrating website files to AWS S3 for static website hosting.
- Configuring Route 53 for domain name management.
- Setting up a GitHub Actions workflow for automated deployment.
- (Optional) Implementing CloudFront for improved performance and global distribution.

## Technical Approach

### Phase 1: Website Preparation and AWS Setup

- **Website Backup**: Download all website files and code from where it is currently hosted. In this case, Hostinger.
- **Version Control**: Create a new GitHub repository to store your website code.
- **AWS Account Setup**: Verify there's an active AWS Account to be used
- **Create an S3 Bucket**: Create an S3 bucket and configure it for static website hosting.

### Phase 2: CI/CD Integration with GitHub to automatically deploy website to S3.

- Push website code to repository
- Configure AWS Credentials:
    - Create an AWS IAM user with programmatic access to S3.
    - Generate access keys for this user.
    - Store these keys securely in GitHub Secrets.
- Create a GitHub Actions Workflow: The worfflow build the website and deploy it to S3 when there's a push to the main branch. 
- Push new Changes to GitHub

### Phase 3: Domain Transfer and DNS Configuration

- Unlock Domain: Unlock your domain in your Hostinger account.
- Obtain Authorization Code: Get the authorization code from Hostinger.
- Transfer Domain to AWS Route 53: Initiate the domain transfer in the AWS Route 53 console using the authorization code.
- Configure DNS in Route 53:
  - Create a hosted zone for your domain.
  - Create an A record pointing to the S3 bucket's endpoint.
 
### Phase 4: CloudFront Implementation ( Optional )

- Create a CloudFront Distribution that points to the S3 hosting the website
- update the alias record in Route 53 to point to the new CloudFront distribution
 
### Phase 5: Test and Monitor

- Test Website: Thoroughly test your website to ensure it's working correctly.
- Monitor Performance using CloudWatch: 
    - Enable CloudWatch Logs for Your S3 Bucket
    - Create a CloudWatch Alarm
    - Use CloudWatch Insights to Analyze Logs
- Implement Security: Ensure your S3 bucket and website are secure.



## Architectural Diagram 

![Cloud Architecture Lucidchart](https://github.com/user-attachments/assets/fb40e356-da3d-4b2d-b7cc-ffb3e6bf814e)



## Project schedule

| Task | Estimated Duration      | 
|:--------:| -------------:|
| Phase 1 & Phase 2 | 1 day |
| Phase 3 | 1 day |
| Phase 4 & 5 | 1 -2 days |



## Potential Challenges


- Domain Transfer: Transferring the domain to AWS Route 53 might require additional steps and time.
- DNS Propagation: DNS changes may take some time to propagate globally.
- S3 Bucket Configuration: Incorrect S3 bucket configuration can lead to website access issues.


## Success Criteria

- Successful migration of the AtrMotors.com website to AWS S3.
- Domain name resolution pointing to the S3 bucket.
- Automated deployment pipeline using GitHub Actions.
- Improved website performance and security.

## Risks and Mitigation Strategies

- Downtime during migration: Schedule the migration during off-peak hours and minimize downtime.
- Unexpected technical issues: Have a rollback plan in place to revert to the original hosting if necessary.
- Security vulnerabilities: Conduct thorough security testing before deploying the website on AWS.

**Please note**: This is a high-level project plan, and adjustments might be necessary based on the specific details of AtrMotors.com and its hosting setup.


This document outlines the migration process, configurations, and CI/CD pipeline setup for AtrMotors.com. Detailed documentation for each step will be maintained in this GitHub repository.




