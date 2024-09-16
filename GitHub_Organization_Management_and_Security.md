# GitHub Organization Management and Security

## Overview

This document outlines how we manage and secure our GitHub organization and its child repositories. The focus is on ensuring that access is restricted, authorized, and properly audited at the platform level, rather than at the individual codebase level. This ensures that changes to the overall GitHub environment, settings, and access are controlled and meet security and compliance standards.

Our approach ensures compliance with access restriction requirements by defining how organizational management, access controls, and auditing are enforced at the GitHub organization level.

## Access Control for GitHub Organization

We implement strict access control at the organizational level to ensure that only authorized personnel can manage the GitHub organization, child repositories, and their associated roles and permissions.

### GitHub Organization Owners/Admins

- **Full administrative control** over the GitHub organization and all child repositories.
- **Responsible for managing access**, creating repositories, configuring security policies, and adjusting roles and permissions across the entire organization.
- **Approval of organizational-level changes**, including access controls, repository creation, and security configurations.
- **Organization Owners/Admins** have the highest level of access and must approve any changes that impact the organization as a whole.
- **Access is assigned via GitHub Teams**, and only the organization can create teams for repositories to ensure consistent control over access management.

### Repository Admins

- **Administrative control over specific repositories** but do not have organization-wide permissions.
- **Responsible for managing repository-specific settings**, managing contributors, and enforcing branch protection rules at the repository level.
- **Approval of repository-level changes**, such as contributor access or repository settings, must be managed by the respective **Repository Admin**.

- **Quarterly Access and Membership Reviews**:
  - Access permissions for both **Organization Owners/Admins** and **Repository Admins** are reviewed quarterly to ensure that only authorized personnel retain access.
  - Permissions are revoked promptly when personnel no longer require access to the organization or specific repositories.

## Platform Management and Change Control

To maintain control over the GitHub organization and its child repositories, we have established processes to ensure that all changes at the platform level are properly managed and authorized.

### Platform-Level Change Requests

- **Requesting Changes**:
  - Any changes to the GitHub organization’s configuration (e.g., repository creation, access permissions, security settings) must be requested through the **Data Solutions mailbox** at <DataSolutions-Solutiondedonnees@ssc-spc.gc.ca>.
  - Changes to the organization as a whole, including access controls and security settings, are handled by **GitHub Organization Owners/Admins**.
  - Changes at the repository level, such as managing contributors or enforcing branch protection rules, are handled by **Repository Admins**.

- **Documenting Changes**:
  - All changes must be documented, and the reasoning behind each change is tracked via email/email chains to ensure traceability.
  - Organization-level changes must be approved by an **Organization Owner/Admin**.
  - Repository-specific changes must be approved by the respective **Repository Admin**.

- **Access via GitHub Teams**:
  - Access to repositories is assigned via **GitHub Teams**. Only the **GitHub Organization Owners/Admins** have the authority to create teams that manage access to repositories.
  - Teams are used to control access, ensuring that the correct permissions are granted to the appropriate personnel at both the organization and repository levels.

- **Approving Changes**:
  - Any modification to sensitive configurations (such as security settings or access controls) must undergo a thorough review by the appropriate **Organization Owner/Admin** or **Repository Admin**, based on the level of the change.
  - The Data Solutions mailbox will be used to document requests and approvals for traceability via email/email chains.

### Child Repository Management

- **Repository Creation**:
  - The creation of new repositories within the organization requires approval from **Organization Owners** to ensure that they meet the organization’s security and governance policies.
  - Repositories must follow standardized naming conventions and inherit organization-wide security policies.

- **Access Restrictions**:
  - Repository access is controlled through organization-level role assignments (e.g., Owners, Administrators, and Contributors).
  - Sensitive repositories may have additional access restrictions, with approval from **Organization Owners** for access changes.

## Auditing and Logging

Auditing and logging play a critical role in ensuring that organizational changes and access modifications are traceable and meet security requirements.

- **Audit Logs**:
  - GitHub’s audit log feature captures critical events such as repository creation, access changes, role modifications, and settings changes at both the organizational and repository levels.
  - **Log reviews** are conducted by individuals delegated with a GitHub security role, ensuring oversight by personnel responsible for monitoring and enforcing security practices.

- **Log Retention**:
  - **Audit logs are retained for 180 days** to support after-the-fact analysis in case unauthorized changes are detected or suspected.
  
- **Audit Frequency**:
  - Audits are conducted **monthly** to review organizational-level changes and ensure adherence to access control policies.
  - **Ad-hoc audits** may also be conducted when specific situations require deeper analysis or in response to potential security incidents.

- **After-the-Fact Analysis**:
  - Audit logs allow retrospective investigations of unauthorized changes or suspicious activity. These logs provide insight into who made changes and under what circumstances, supporting incident response and remediation efforts.

## Security Measures for the GitHub Organization

To secure the GitHub organization and its child repositories, we enforce the following security measures:

- **Organization-Wide Security Settings**:
  - The GitHub organization enforces strict security settings, including **branch protection rules**, **two-factor authentication (2FA)**, and **secret scanning** to protect sensitive repositories.
  - **Third-party integrations** are restricted and must be approved by an **Organization Owner** to ensure that they align with organizational security policies.

- **Multi-Factor Authentication (MFA)**:
  - All users with elevated privileges (e.g., Organization Owners, Administrators) must use MFA to access the GitHub platform.
  - MFA ensures that even if credentials are compromised, additional security is required for access to the organization.

- **Secret and Code Scanning**:
  - Secret scanning is enabled across all repositories to detect and prevent the exposure of sensitive information, such as API keys and credentials.
  - Any detected secrets are flagged, and remediation steps are taken immediately.

- **Dependency Scanning**:
  - Automated dependency scanning tools are used to identify vulnerable third-party libraries and ensure that all repositories remain up to date with security patches.

## Organizational Admin Access Guidelines

While GitHub provides logical controls, we have established additional guidelines for **Organization Admin Access**:

- **Admin Access Agreement**:
  - Organization admin accounts will agree to only access the GitHub platform using SSC-provided machines while connected to Government of Canada (GC) networks. This practice helps ensure that admin-level access is conducted from secure environments.
  - However, we acknowledge that there is no direct enforcement mechanism for this at the GitHub platform level.

## Summary

Our approach to managing and securing the GitHub organization and its child repositories ensures that platform-level changes are properly reviewed, authorized, and audited. By enforcing access controls, security measures, and periodic audits, we maintain the integrity and security of the GitHub environment.

Regular access reviews, quarterly membership reviews, monthly audits, and retention of audit logs for after-the-fact analysis ensure that any unauthorized changes are detected and addressed promptly. Additionally, multi-factor authentication and secret scanning further strengthen our security posture across the organization.

This document serves as a guide to how we manage and secure the GitHub organization and its repositories. For any questions or further clarification, feel free to contact the organization admins or review our security policies.
