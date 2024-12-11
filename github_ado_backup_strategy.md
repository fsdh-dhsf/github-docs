# Backing up GitHub to Azure DevOps&#x20;

Satisfying CP-9 security controls.&#x20;

## Overview

This document provides evidence of compliance with the CP-9 control, which mandates the creation, security, and verification of backups for critical systems. By implementing a mirroring process for GitHub repositories to an enterprise-managed Azure DevOps (ADO) instance, we ensure that vital data and configurations are consistently backed up and safeguarded. This approach helps reduce the risk of data loss, ensures consistent availability, and supports recovery in case of unexpected disruptions.

## Backup Implementation

### Understanding Git Repository Cloning

Cloning a Git repository is more than just copying files; it creates a complete backup of the repository's history, including all changes, branches, and tags. This ensures that every past version of the code and its metadata are preserved. Unlike a simple filesystem or a compressed archive, Git tracks every modification and allows for precise reconstruction of any state of the repository. This makes it a powerful tool for ensuring the integrity and completeness of backups.

### Scope of Backups

- **Repositories Included**:
  - All GitHub repositories containing code, configurations, and other essential project data are included in the backup process. This comprehensive coverage ensures no critical data is missed.
- **Backup Frequency**:
  - Backups are triggered every 6 hours to ensure frequent synchronization of repository data, reducing the time window for potential data loss in case of failures.

### Backup Methodology

- **Mirroring**:
  - The backup process involves cloning each GitHub repository as a mirror, which includes all branches and tags. This approach guarantees that every detail of the repository is captured and stored securely.
- **Automated Pipeline**:
  - An Azure DevOps pipeline has been configured to:
    - Validate permissions using the Azure DevOps service token, ensuring secure access.
    - Clone GitHub repositories completely to capture the current state.
    - Push mirrored repositories to Azure DevOps for safe storage and redundancy.

### Storage Location

- **Azure DevOps Instance**:
  - Backups are stored in a corporate-managed Azure DevOps instance, which adheres to enterprise-level security and compliance standards.
  - This setup ensures compliance with confidentiality, integrity, and availability requirements by inheriting the enterprise’s robust security policies and disaster recovery measures.

### Security Measures

- **Access Control**:
  - Backup repositories in ADO are protected by enterprise-managed access controls to prevent unauthorized modifications. These are mirrors of public repositories from GitHub, where the code is open source. While our ADO instance is private, the mirrored code remains consistent with the public and open-source nature of the original GitHub repositories.
  - Only ADO users who are part of the FSDH team in ADO will have access to the backups, ensuring that access to backups is limited to authorized personnel.
- **Encryption**:
  - Data is transmitted securely via HTTPS and is encrypted at rest to ensure its confidentiality and integrity. This protects the data from being accessed or modified by unauthorized entities during transmission or storage. Additionally, every change and every file in the Git repositories is cryptographically signed, ensuring tampering is not possible and preserving the integrity of the repository data.

## Verification of Backups

### Testing Procedures

- **Restore Validation**:
  - The pipeline automatically verifies backups by downloading the mirrored repositories from ADO and performing a file integrity check using Git commands. This includes running `git fsck` to validate repository integrity, listing remote branches, verifying tags, and displaying the latest commit to ensure all mirrored data is accurate and complete.

### Documentation of Results

- **Logs**:
  - Detailed logs of backup operations and verification activities are maintained within Azure DevOps. These logs provide a clear record of all actions taken during the backup process, supporting traceability and compliance.
  - Logs include timestamps, repository names, and results of push operations, offering complete transparency into the backup workflow.

### Pipeline Configuration Details

- **Trigger** Schedule:
  - The pipeline runs every 6 hours via a CRON schedule, ensuring frequent and reliable backups without manual intervention.
- **Script Details**:
  - The pipeline script checks for valid tokens, makes exact copies of repositories, and saves them in Azure DevOps for safekeeping. It is designed to handle errors effectively and provide detailed feedback in case of failures.

### Key Steps in the Pipeline:

1. **Token Validation**:
   - Ensures the System.AccessToken has necessary permissions to perform backup operations securely and reliably.
2. **Repository Cloning**:
   - Mirrors the GitHub repository to include all branches and tags, capturing the complete state of the repository at the time of backup.
3. **Repository Push**:
   - Pushes the cloned data to the designated ADO backup repository with force updates to ensure a complete overwrite of the existing state, maintaining consistency.

## Summary

The implementation of the described Azure DevOps pipeline satisfies the CP-9 control by:

- Ensuring regular and automated backups of critical GitHub repositories, with updates synchronized every 6 hours.
- Safeguarding backups within a secure enterprise-managed Azure DevOps instance, leveraging its robust security policies.
- Verifying the integrity of backups through periodic testing, including restore validation and automated code testing, to ensure functionality and accuracy.
- Providing a clear audit trail with comprehensive logging of all backup and verification activities.

This process provides a robust mechanism to protect critical project data, ensure its availability in the event of unforeseen disruptions, and maintain compliance with CP-9 security controls.

