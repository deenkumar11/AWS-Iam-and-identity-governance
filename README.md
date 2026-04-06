# AWS IAM & Identity Governance

A hands-on AWS administration project simulating enterprise-scale 
identity and access management for a fictional company using AWS 
Organizations, IAM, and IAM Identity Center.


## Project Overview

This project mirrors real-world cloud administrator responsibilities 
around user lifecycle management, least-privilege access, SSO, and 
audit logging — built entirely on AWS Free Tier.


## Architecture

Root (Management Account)
├── Production OU → Region Restriction SCP
├── Development OU → MFA Enforcement SCP
└── Security OU

IAM Identity Center (SSO Portal)
├── alice.admin → AdminAccess Permission Set
└── bob.dev → DeveloperAccess Permission Set

IAM Structure
├── Groups: Admins, Developers, ReadOnlyOps, BillingTeam
├── Custom Policies: DeveloperPolicy, BillingReadOnlyPolicy
└── Roles: EC2-S3ReadOnly-Role, CrossAccount-ReadOnly-Role

## SERVICES USED

1. AWS ORGANIZATIONS - to organize the workflow by creating different organizational units for each team.

2. SCP -  Service Control Policies had been implemented and attached to different organizations to get a control over the organization by restricting region level access for production team and enforcing MFA for the development team.

3. IAM Users,Groups and Roles - IAM users were created for each persona (Admin, Developer, Read-Only Ops, and Billing) and organized into groups, with custom JSON policies attached at the group level to enforce least-privilege access — ensuring each team could only interact with the AWS services required for their role.

4. IAM Identity Center - IAM Identity Center was enabled to provide centralized SSO access and users were created and assigned permission sets then attached to the AWS account so that users can login through a single SSO portal instead of managing separate IAM credentials for each account.
