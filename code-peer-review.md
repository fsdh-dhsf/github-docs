# Peer Review Process for GitHub Repositories

## Overview

This document explains our peer review process for changes made to GitHub repositories. Peer review is an important practice that helps us keep our code safe, reliable, and of high quality. It ensures that changes are reviewed, discussed, and approved before they are integrated into the main codebase, reducing the risk of errors and security issues.

Our peer review process is conducted through **pull requests (PRs)**, which allow us to propose changes, receive feedback, and approve updates before adding them to the repository.

## Pull Request Workflow

### Step 1: Opening a Pull Request

- **Choose an Issue**: To start contributing, pick an issue from the issues page and assign it to yourself.
- **Create a Branch**: Create a new branch from the `develop` branch. Preferably, start the branch name with your initials (e.g., `fl/branch_name`). This keeps the `develop` branch stable while changes are being reviewed.
- **Propose Changes**: To make changes to the codebase, create a **pull request** (PR) in GitHub. The PR should include a description of what was changed, why it was changed, and any other important details.
- **Open the Pull Request**: Go to the Pull Requests page and click **New pull request**. Select the `develop` branch as the base branch and your branch as the one to be merged.

### Step 2: Assigning Reviewers

- **Code Owners**: When the pull request is created, **reviewers** are automatically assigned based on our **CODEOWNERS** file. This file defines who is responsible for reviewing specific parts of the codebase.
- **Code Owner Approval**: At least one code owner must approve the pull request before it can be merged. This ensures that knowledgeable team members are involved in the review process. Reviewers can also be manually assigned if needed.

### Step 3: Reviewing the Pull Request

- **Code Review**: Reviewers examine the changes in the pull request. They check that the changes follow security best practices and do not introduce any issues. Reviewers provide constructive feedback to help improve the code.
- **Discussion and Feedback**: Reviewers may leave comments, request changes, or ask questions to clarify the changes. Contributors are expected to address this feedback and update the pull request as needed. Reviewers will re-evaluate the changes until all concerns are resolved.
- **Approval**: Once reviewers are satisfied with the changes, they **approve** the pull request. This means the changes are ready to be merged.

### Step 4: Merging the Pull Request

- **Merge Conditions**: A pull request can only be merged if all reviewers approve it and all required **status checks** (such as automated tests) pass.
- **Merging**: Once all requirements are met, an authorized contributor can merge the pull request. This integrates the changes into the main codebase.

## Branch Protection Rules

To ensure that the peer review process is followed, we use **branch protection rules** to make sure changes to the main branch are reviewed and approved before being merged.

- **Require Pull Request Reviews**: Branch protection rules require that changes to the main branch must be made through pull requests, which must be reviewed and approved by at least one reviewer.
- **Code Owner Enforcement**: **CODEOWNERS** are automatically assigned to review specific parts of the code, and at least one code owner must approve the pull request before it can be merged.
- **Status Checks**: All required status checks (e.g., unit tests, code scans) must pass before a pull request can be merged. This ensures that the code is reviewed by both team members and automated tools.

## Automated Testing and Code Scanning

As part of the peer review process, we use automated tools to run **unit tests** and perform **code scanning** whenever a pull request is opened or updated. These automated checks help maintain the quality and security of our codebase:

- **Unit Tests**: All relevant unit tests are automatically run to verify that new changes do not break existing functionality. Contributors are responsible for adding or updating tests as needed.
- **Code Scanning**: Automated code scanning tools check for security vulnerabilities, bugs, or other issues. Any flagged issues must be resolved before the pull request can be approved.

These automated checks work alongside peer reviews to ensure that every change is thoroughly reviewed, helping catch issues early.

## Pull Request Template

For reference, the following template is used when creating a pull request:

```
# Pull Request

## Description
<!-- A brief description of what this PR does -->

## Related Issues
<!-- List any related issues or tickets -->

## Changes
<!-- List the key changes in this PR -->
- Change 1
- Change 2
- Change 3

## Testing
<!-- Describe the tests that were run or any QA steps that were taken -->
- Test 1
- Test 2

## Checklist
<!-- Ensure the following tasks are complete -->
- [ ] Code follows best practices
- [ ] Tests added/updated to cover changes
```

## Requirements for Passing Peer Review

To pass the peer review process, the following requirements must be met:

- **Assigned Reviewers**: At least one code owner or assigned reviewer must approve the pull request.
- **Constructive Feedback Addressed**: All feedback provided by reviewers must be addressed, and any requested changes must be made before the PR can proceed.
- **Automated Tests**: All relevant unit tests must pass successfully. Contributors are responsible for adding or updating tests as needed.
- **Code Scanning**: Code scanning must not identify any critical or high vulnerabilities or issues. Any flagged issues must be resolved.
- **Branch Protection Rules**: The PR must comply with branch protection rules, including status checks and code owner enforcement.

## Summary

Our peer review process is conducted using GitHub pull requests, ensuring that every change to our codebase is reviewed by authorized team members before being merged. This helps maintain the security, reliability, and quality of our code, while also encouraging collaboration. If you have any questions, please contact the repository administrators or refer to our internal contribution guidelines.


