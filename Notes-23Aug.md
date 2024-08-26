# IAM User Limits and Groups

## IAM User Limits
- An IAM user can be a member of up to **10 groups**.
- There is a limit of **5000 IAM users** per AWS account.

## IAM Groups
- **IAM groups** are containers for users.
- Multiple IAM users can belong to multiple groups.
- **IAM groups** are not real identities, meaning:
  - They cannot log in.
  - They do not have credentials.

### Benefits of IAM Groups
1. **Administrative Management:** Groups can represent projects, teams, or functional units within a business.
2. **Policy Management:** You can attach policies to groups (both inline and managed), which are then merged into a single permission set for all users within the group.

### Limits of IAM Groups
- **No Nesting:** IAM groups cannot contain other groups.
- **Group Limit:** Each AWS account can have a maximum of **300 groups**.

## Resource Policies
- A **resource policy** is attached directly to a resource (e.g., an S3 bucket).
- Example: A bucket can have a policy that allows specific users like "Sally" to access it.
- Policies can reference IAM users and roles by using their **ARN** (Amazon Resource Name).
