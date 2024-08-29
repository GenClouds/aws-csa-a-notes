# AWS Control Tower

**Another evolution to AWS Organizations providing extra features, automation, and intelligence.**

## Key Features

- **Quick and easy setup** of multi-account environment.
- **Orchestrates other AWS services** to provide this functionality.
- Uses Organizations, IAM Identity Center (AWS SSO), CloudFormation, Config, and many more.

> **Provides landing zone** - multi-account environment, this is for the AWS Organizations with superpowers.

### Well-Architected Multi-Account Environment

- **Home Region**: Built with AWS Organizations, AWS Config, CloudFormation.
- **Security OU**: Log archive and audit accounts (CloudTrail and Config logs).
- **Sandbox OU**: Test/less rigid security.
- Also can create other OUs and accounts.

### Utilizing IAM Identity Center

- AWS SSO, multi-account, ID federation.
- **Monitoring and Notification**: CloudWatch and SNS.

## Centralized Logging and Auditing

- **SSO/ID Federation**: Centralized logging and auditing.

> **Provides Guardrails**:
- Detect/mandate/rules/standards across all accounts.
- Rules for multi-account governance.
- Three types: Mandatory, Strongly Recommended, and Elective.
- Function in two different ways:
  1. **Preventive**: Stop you from doing things (AWS Org SCP).
     - Enforced or not enabled.
  2. **Detective**: Compliance check (AWS Config Rules).

## Account Factory

- **Automates and standardizes** new account creation.
- Automated account provision.
- Cloud admins or users with appropriate permissions.
- Accounts to be closed or repurposed.
- Integrated with SDLC lifecycles.
- Can be used for account testing.

- `remember` :
  #### landing zone
  #### gaurd trails
  #### factory account
  
- 
