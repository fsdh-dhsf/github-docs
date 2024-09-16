# Securing Our Code Against Supply Chain Attacks

## Overview

Our organization takes the security of our code seriously, particularly the risk of supply chain attacks. These attacks, which exploit vulnerabilities in dependencies, libraries, or the build pipeline itself, pose a critical threat to the integrity of our systems. To safeguard against these threats, we have implemented a comprehensive strategy built on the following pillars:

1. **SBOM Generation**
2. **Dependency Management**
3. **Code Scanning & Static Analysis**
4. **Secret Scanning**
5. **Alert Management and Monitoring**

These safeguards ensure that our code remains secure throughout the entire software development lifecycle, from development to deployment.

## Supply Chain Protection Strategy

### 1. **SBOM Generation**

We generate a **Software Bill of Materials (SBOM)** for all projects, providing a comprehensive inventory of all components, dependencies, and libraries used. This SBOM serves as an essential record for tracking the origin and version of each component, helping us quickly identify and remediate any vulnerabilities that may arise.

**How We Do It**:
- The SBOM is generated automatically using our GitHub Actions workflows upon every build or push to the main branch.
- It is regularly reviewed and updated to reflect any changes in the project’s dependencies.

### 2. **Dependency Management**

Our dependency management strategy is designed to mitigate risks from third-party libraries and packages. We automate the detection of outdated or vulnerable dependencies using GitHub's **Dependabot**.

**Key Actions**:
- Dependencies are automatically scanned for vulnerabilities, with alerts generated for any outdated or vulnerable components.
- When vulnerabilities are identified, pull requests are automatically created to upgrade the affected dependencies.
- We pin critical dependencies to specific, trusted versions to prevent unexpected updates from introducing new vulnerabilities.

### 3. **Code Scanning & Static Analysis**

We perform **automated code scanning and static analysis** on all repositories to identify vulnerabilities, bugs, and potential security issues in both our code and the dependencies we rely on.

**Tools and Practices**:
- GitHub’s built-in **code scanning** is configured to scan for known vulnerabilities in dependencies as well as potential issues within our code.
- Static analysis tools are run automatically during the CI/CD pipeline to check for coding errors, security flaws, and compliance with coding standards.
- All findings are triaged and addressed promptly based on severity.

### 4. **Secret Scanning**

We use **secret scanning** to detect sensitive data, such as API keys, credentials, and tokens, accidentally committed to our repositories. This prevents sensitive information from being exposed in public or internal repositories, reducing the risk of supply chain compromise through leaked credentials.

**How We Implement This**:
- Secret scanning is enabled on all repositories, scanning for common patterns that resemble sensitive data.
- Alerts are generated if any secrets are detected, prompting an immediate response.

### 5. **Alert Management and Monitoring**

Our alert management system captures and consolidates all security-related alerts, providing visibility into potential threats and allowing us to respond in a timely manner. We send these alerts to the following destinations:
- **Teams Support Channel**: Provides real-time visibility and collaboration for immediate response.
- **Security Alerts Mailbox**: Centralized inbox for storing all security notifications.
- **Log Analytics Workspace (WIP)**: We are currently working on forwarding these alerts to a **Log Analytics Workspace** for long-term storage and correlation with other logs. This future integration will allow us to perform deeper analysis and improve incident response.

By integrating our security alerts into multiple channels, we ensure that potential risks are promptly identified and addressed by the appropriate teams.

## Incident Reporting & Communication

Our **SECURITY.md** policy provides clear guidelines on how to report security vulnerabilities:


## Future Enhancements

To continually improve our security posture, we are planning the following enhancements:
- **Log Analytics Workspace**: Once completed, this will provide deeper integration for long-term storage and correlation of security alerts with other operational logs.
- **Tamper-Evident Practices**: Implement tamper-evident packaging for critical components during shipping and storage.
