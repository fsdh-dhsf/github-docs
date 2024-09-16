# Codebase Management and Security in GitHub

## Overview

This document outlines how we manage and secure our codebases in GitHub, ensuring that changes are controlled, authorized, and audited. It details the key practices, controls, and workflows used to maintain the security, integrity, and quality of our code.

Our approach ensures compliance with access restriction requirements by defining who can make changes, how those changes are reviewed and approved, and how records of access and changes are maintained for audit purposes.

## Access Control for Codebases

We implement strict access control to ensure that only authorized personnel can make changes to our codebases. Our access controls are structured as follows:

- **Repository Owners/Admins**:
  - Full control over repository settings, including branch protection, access management, and permissions.
  - Responsible for maintaining access rules, managing roles, and ensuring that only qualified individuals can approve and merge changes.

- **Repository Code Contributors**:
  - Have write access to the repository but are **restricted from pushing directly** to default branches.
  - All changes made by contributors must go through the pull request (PR) process, which requires review and approval by another contributor or repository owner before being merged.

- **Contributors**:
  - Can submit pull requests from forks but do not have direct write access to the repository. 
  - Their contributions must be reviewed and approved by authorized personnel.

- **Periodic Access Reviews**:
  - Access permissions are reviewed periodically to ensure that only the necessary individuals retain access to the repositories. When personnel no longer require access, their permissions are revoked promptly.

## Branch Protection for Codebases

We use GitHub's branch protection features to enforce the following security measures on our default branches:

- **Protected Branches**:
  - Default branches are protected, and changes cannot be made directly.
  - Branch protection rules enforce that changes are only made through approved pull requests.

- **Required Reviews**:
  - All pull requests must be reviewed and approved by at least one other authorized contributor before being merged.
  - The reviewer must be someone other than the original submitter to ensure independent oversight.

- **Required Status Checks**:
  - Before a pull request can be merged, all required CI/CD checks (such as tests and security scans) must pass successfully. This helps catch issues early and ensures that only stable, secure code is merged into the default branches.

- **Merging Restrictions**:
  - Only authorized personnel, such as **Repository Owners/Admins** and approved **Code Contributors**, can merge pull requests into protected branches.

## Change Management for Codebases

All changes to the codebase follow a structured workflow designed to ensure that changes are reviewed, tested, and approved by the appropriate personnel.

### Pull Request Workflow

- **Submission**:
  - All changes to the codebase must be submitted via pull requests. Contributors are required to submit PRs for any modifications they make.

- **Review and Approval**:
  - Pull requests are reviewed by another **Code Contributor** or **Repository Owner/Admin**. Reviewers assess the code for functionality, security, and adherence to coding standards.
  - The review process is documented, and any approvals or rejections are recorded in the pull request logs to ensure full traceability of decisions.

- **Merging**:
  - Only after the review is completed, and all required checks pass, is the pull request eligible to be merged into the default branch.
  - Merges must be approved by someone other than the original submitter.
  - All approved merges are logged for auditing purposes.
 
    
## Auditing and Logging

To ensure accountability and traceability, we rely on GitHub's audit log features to track all actions related to the codebase. These logs are essential for identifying any unauthorized changes and ensuring compliance with our security standards.

- **Audit Logs**:
  - GitHub’s audit logs capture critical events such as who accessed the repository, who made changes, and who merged pull requests. These logs provide detailed tracking of changes to the codebase.
  - **Log reviews** are conducted by individuals delegated to the GitHub security role, ensuring oversight by personnel responsible for monitoring and enforcing security practices.
  - **Audit logs are retained for 180 days** to support after-the-fact analysis if unauthorized changes are suspected.

- **Audit Frequency**:
  - Audits are conducted **monthly** to review logs and ensure adherence to access controls and security processes.
  - **Ad-hoc audits** may also be conducted when specific situations require deeper analysis or in response to security incidents.

## Security Measures

In addition to access control and branch protection, we implement the following security measures to safeguard our codebase:

- **SBOM Generation**:
  - We generate a **Software Bill of Materials (SBOM)** for all codebases to track the components, dependencies, and libraries used. This helps ensure that we can quickly identify and address vulnerabilities in third-party components.

- **Dependency Scanning**:
  - Automated dependency scanning tools (such as Dependabot) monitor our codebases for outdated or vulnerable dependencies. These scans generate alerts that are reviewed and acted upon as needed.

- **Code Scanning and Static Analysis**:
  - We use automated code scanning and static analysis tools to continuously monitor our codebase for security vulnerabilities, bugs, and other issues. Any flagged issues are reviewed and remediated before changes are merged.

- **Secret Scanning**:
  - We use GitHub's secret scanning features to ensure that no sensitive data (e.g., API keys, credentials) is accidentally committed to the repository. Any detected secrets are flagged, and remediation steps are taken immediately.

## Physical and Logical Access Controls

While GitHub implements logical access controls through roles and permissions, we also encourage the following practices for organization admins:

- **Organization Admin Access**:
  - Organization admin accounts will agree to only access the GitHub platform using SSC-provided machines while connected to Government of Canada (GC) networks. This practice ensures that admin-level access is conducted from secure environments.
  - However, it is important to note that we currently do not have a way to enforce this restriction directly within the GitHub platform.

- **Multi-Factor Authentication (MFA)**:
  - Access to GitHub is protected by multi-factor authentication (MFA), ensuring that even if credentials are compromised, additional security is required for access.

## Summary

Our approach to managing and securing codebases in GitHub ensures that changes are properly reviewed, authorized, and audited. By enforcing access control, branch protection, and comprehensive security measures, we maintain the integrity and security of our code throughout its lifecycle. 

Periodic access reviews, monthly audits, and after-the-fact analysis capabilities ensure that any unauthorized changes are detected and addressed. Physical and logical security measures, including MFA and network controls, further secure access to our GitHub environment.

This document serves as a guide to how we handle codebases in our GitHub environment. For any questions or further clarification, feel free to contact the repository admins or review our security policies.
