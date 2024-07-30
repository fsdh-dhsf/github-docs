# GitHub Strategy for Federal Science Data Hub (FSDH)

## Purpose

The purpose of this strategy is to outline how the Federal Science Data Hub (FSDH) will manage its codebase across GitHub and Azure DevOps, ensuring the balance between collaboration, open-source contribution, and the security of sensitive components, including the protection of personal information and adherence to privacy impact assessments (PIA).

## Overview

FSDH is committed to leveraging the strengths of both GitHub and Azure DevOps to facilitate efficient, secure, and collaborative development. This strategy details the approach for segregating our codebase to optimize for public engagement while ensuring the protection of sensitive and protected information. Additionally, this strategy incorporates SecDevOps practices and aims to transition to a GitOps model.

FSDH initially started on GitHub with the [NRCan datahub-portal](https://github.com/NRCan/datahub-portal) and will continue to leverage GitHub for public collaboration while managing sensitive components securely on Azure DevOps.

## Codebase Segmentation

### Public Code on GitHub
- **Objective**: Promote collaboration, transparency, and community contributions with Government of Canada (GC) employees and Canadian citizens.
- **Components**:
  - **Non-sensitive code**: Any code that does not contain sensitive information.
  - **Documentation**: General documentation, tutorials, and usage guides.
  - **Open-source tools and libraries**: Reusable components, utilities, and tools developed by FSDH that can benefit the broader scientific community.
  - **Demo projects**: Sample demo projects, templates and Jupyter notebooks can help scientists kickstart new projects.
- **Management**:
  - Regular reviews to ensure no sensitive information is inadvertently included.
  - Clear contribution guidelines to manage external contributions.
  - Continuous integration (CI) pipelines for public repositories to maintain code quality and integration.
  - Every change goes through rigorous pull request process with peer reviewing plus automated regression testing before being merged
  - FSDH Follows industry best practices for sharing and managing public code

### Sensitive Code on Azure DevOps
- **Objective**: FSDH follows industry best practices, leading open source projects and uses Azure DevOps to protect sensitive and proprietary information, including secrets and personal information, while ensuring robust development and deployment workflows.
- **Components**:
  - **Confidential code**: Code that deals with sensitive data, proprietary algorithms, or anything requiring restricted access.
  - **Secrets and protected information**: Any data or information that is protected under PIA or any other regulatory compliance.
  - **Deployment scripts**: Scripts and configurations used for deploying applications to production environments.
  - **Internal tools and libraries**: Components used internally by FSDH that should not be exposed publicly.
- **Management**:
  - Azure DevOps follows existing governance processes
  - Strict access controls and permissions to ensure only authorized personnel have access.
  - Secure CI/CD pipelines to automate testing and deployment processes without exposing sensitive information.
  - Regular audits and compliance checks to ensure adherence to security policies, including those required by PIA.

## Integration and Collaboration

### Cross-Platform Integration
- Utilize GitHub Actions to trigger processes in Azure DevOps where necessary.
- Implement webhooks and API integrations to synchronize actions between GitHub and Azure DevOps.

### Collaboration Workflow
- Encourage open collaboration on GitHub for public components, allowing external contributors, including GC employees and Canadian citizens, to fork, submit issues, and create pull requests.
- Internal teams will use Azure DevOps for developing sensitive components, with periodic syncs or releases to GitHub where applicable.

## SecDevOps Practices

### Security Integration
- Integrate security practices into the development process from the start, ensuring that code is secure by design.
- Automate security checks and vulnerability assessments in the CI/CD pipelines on both GitHub and Azure DevOps.
- Vulnerabilities in existing packages will be flagged by Dependabot 

### Continuous Monitoring and Feedback
- Implement continuous monitoring of codebases to detect and respond to security threats in real-time.
- Use automated tools to provide immediate feedback to developers on security issues and code quality.
- GitHub security tools include a secret scanner that will alert the team if any secret is committed by mistake in the public repository
- Remediation process to be documented to handle accidental leakage of secrets in the source code

## Security and Compliance

### Security Measures
- Conduct regular security reviews and vulnerability assessments of both GitHub and Azure DevOps repositories.
- Implement automated tools for scanning codebases for secrets and sensitive information before commits are accepted.
- Ensure all sensitive data, including secrets and protected information, is stored securely on Azure DevOps and is never exposed on GitHub.

### Compliance
- Ensure all public repositories on GitHub comply with open-source licenses, intellectual property regulations, and PIA requirements.
- Maintain compliance with internal and external regulations for all code stored in Azure DevOps.

## Documentation and Training

### Documentation
- Maintain comprehensive documentation for both public and internal codebases.
- Provide guidelines and best practices for contributing to and managing repositories on both platforms.

### Training
- Offer training sessions and resources for team members on using GitHub, Azure DevOps, SecDevOps practices, and GitOps principles effectively.
- Regularly update training materials to reflect changes in tools and processes.

## Monitoring and Review

### Monitoring
- Implement monitoring tools to track activity, contributions, and security alerts on both GitHub and Azure DevOps.

### Review
- Conduct regular reviews of the strategy to ensure it remains effective and aligned with FSDH goals.
- Gather feedback from team members and contributors to continually improve processes.

---

This strategy ensures that FSDH leverages the collaborative power of GitHub while maintaining the security and integrity of sensitive components through Azure DevOps, with a strong emphasis on protecting personal information, complying with privacy impact assessments, and integrating SecDevOps practices. 
