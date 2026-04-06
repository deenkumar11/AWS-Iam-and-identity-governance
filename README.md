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
