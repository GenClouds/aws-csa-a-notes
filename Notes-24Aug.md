# Service Control Policies (SCP)

**Service Control Policies (SCP)** are a feature in AWS Organizations used to restrict AWS accounts. An SCP is a policy document written in JSON format. These policies can be attached directly to the AWS Organization as a whole and can also be applied to one or more Organizational Units (OUs).

### Key Points to Remember

- **Management Root Account Exemption**: In AWS Organizations, the management root account is not affected by SCPs.
- **Account Permission Boundaries**: SCPs serve as permission boundaries, meaning they limit what an account can do.
- **Indirect Restriction**: SCPs can indirectly restrict the account root user, specifically the identities associated with that account.
- **Powerful Tool**: SCPs are especially powerful for managing complex AWS deployments.
- **No Permission Grants**: SCPs do not grant permissions; they only restrict them.

### Two Ways to Use SCP

1. **Allow List vs Deny List**
   - **Deny List by Default**: By default, SCPs operate in a Deny List mode, meaning all AWS services are accessible unless explicitly blocked.
   - **Block by Default**: Alternatively, SCPs can operate in an Allow List mode, where all services are blocked by default, and only specific services are allowed.
   - **Explicit Deny Always Wins**: If there is a conflict between an allow and deny rule, the explicit deny rule always takes precedence.

### Important Considerations

- **Effective Permissions**: The effective permissions for identities within an account are determined by the overlap between identity policies and SCPs.




# CloudWatch Logs

**CloudWatch Logs** is a public, regional service provided by AWS. It can be used from various environments including:

- AWS (from within a VPC)
- On-premises systems
- Other cloud platforms (assuming appropriate AWS permissions and network connectivity)

## Purpose

CloudWatch Logs is primarily used to:

- **Store** logging data
- **Monitor** logs
- **Access** logging data

## Logging Data

At a basic level, logging data consists of:

- Information
- Timestamps (e.g., year, month, day, hours, minutes, seconds, time zones)

## Built-in Integrations

CloudWatch Logs has built-in integrations with several AWS services, including:

- EC2
- VPC Flow Logs
- Lambda
- CloudTrail
- Route 53
- And many more...

## Metric Filters

CloudWatch Logs also has the capability to take logging data and generate metrics through **Metric Filters**.

