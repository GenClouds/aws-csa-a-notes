# AWS CloudTrail Overview

**CloudTrail** is a regional service that logs API actions affecting an AWS account. It stores logs of every action performed within the AWS environment. For instance:

- Stopping an EC2 instance
- Creating or deleting an S3 bucket
- Creating a new security group

These actions are logged as **CloudTrail events**.

## CloudTrail Event

A **CloudTrail event** is a record of an activity within the AWS environment. Actions can be initiated by a user, role, or service. By default, CloudTrail is enabled to store 90 days of event history.

### Types of CloudTrail Events

CloudTrail events can be categorized into three types:

1. **Management Events**
   - Provide information about management operations in the AWS account.
   - Also known as control plane operations.
   - Examples: Creating, terminating EC2 instances, VPC creation, etc.

2. **Data Events**
   - Provide information about resource operations performed on or within a resource.
   - Examples: Uploading objects to S3, accessing objects from S3, invoking a Lambda function.

3. **Insight Events**
   - ### Insight Events

**Insight Events** provide information about unusual activity in your AWS environment. These events help in identifying anomalous behaviors, such as spikes in resource usage or unexpected changes in API activity. By detecting these anomalies, Insight Events enable quicker investigation and remediation of potential security or operational issues.


## Trails

Trails are how you configure CloudTrail to deliver logs to CloudWatch Logs and Amazon S3. By default, management events are logged to the **US East (N. Virginia) Region (us-east-1)**, as they are globally focused services.

### Limitations

- **Not Real-Time**: There is a delay in log delivery.
- **Delay**: It takes approximately 15 minutes for the logs to be delivered after logging.

