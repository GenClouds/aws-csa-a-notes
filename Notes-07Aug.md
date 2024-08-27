## 🚧IAM Access Keys: Your Gateway to AWS 

**IAM users** can interact with AWS services in several ways:

* |Console|A graphical user interface for managing AWS resources|
  |-------|-----------------------------------------------------|
  
* |Command Line Interface (CLI)|A powerful tool for interacting with AWS programmatically|
  |----------------------------|----------------------------------------------------------|
* |APIs|Programmatic access to a wide range of AWS services|
  |----|---------------------------------------------------|

Unlike traditional username and password authentication, AWS CLI use **IAM access keys** for secure access.


## 🔐Understanding IAM Access Keys

**🔐IAM access keys** are long-term credentials used with IAM users to grant programmatic access to AWS resources. Unlike traditional passwords, they don't change automatically and require manual management by the credential owner.

📌 it is made up of two parts :

|Access Key ID|The public part of the credential|
|-------------|---------------------------------|
|Secret Access Key|The private, password-like part of the credential|

**🚩Key Management:**
* Each IAM user can have up to two active access key pairs.
* Access keys can be created, deleted, activated, or inactivated.

By default, newly created access keys are active.
## IAM Access Key Components

An IAM access key consists of two essential parts:

1. **`Access Key ID`:** A unique identifier for the access key, similar to a username (e.g., `AKIAIOSFODNN7EXAMPLE`).
2. **`Secret Access Key`:** A long, complex, and  password used for authentication (e.g., `AKIAIOSFODNN7EXAMPLEYXBQ`).

**📝Note to Remember :**

* Never share your secret access key with anyone.
* Store the access key information securely, such as in a password manager or a downloaded CSV file.
* While IAM users have access keys, IAM roles do not.
## Rotating Access Keys

**♻️Rotating access keys** involves deleting old credentials and generating new ones to enhance security.

**Creating IAM Access Keys:**

* while configuring access keys , we should be careful.
* Once created, access keys cannot be retrieved.
* While IAM users can have access keys, IAM roles do not. IAM roles are temporary security credentials assigned to resources (e.g., EC2 instances) and are generally considered more secure than access keys 

## 💡 Creating IAM Access Keys (**Use IAM Roles First if Possible**)

 It is strongly recommended to use IAM roles whenever possible,because Roles are temporary and don't require manual rotation, reducing the risk of compromised credentials.

**🛂If you must create access keys, follow these steps:**

* **Log in** to the AWS Management Console using your root account credentials. 

* **Navigate** to the IAM service. 

* **Select** the user for which you want to create an access key.    

* Go to the "Security credentials" tab.    

* **Click** on "Create access key".

 Download the **CSV file** containing the access key ID and secret access key. **This file is only available once**, so store it securely (ideally in a password manager). 
  ## Access Key Management

An individual AWS account can have **up to two sets of access keys**. These access keys can be **recreated, deleted, activated, or inactivated** as needed.
 ## AWS CLI v2: 
 AWS  command line interface  version 2
 
The AWS CLI v2 is the latest version of the AWS Command Line Interface, providing improved performance and features for accessing AWS products and services.

##  COMMANDS 

> Common AWS CLI v2 Commands

* |`aws`|The base command for interacting with AWS services & products|
  |---|-------------------------------------------------------------|
* |`aws --version`|Displays the installed version of the AWS CLI|
  |---------------|---------------------------------------------|
* |`aws configure --profile IAMADMIN-Generalaccount`        |Sets up credentials for a profile named `IAMADMIN-Generalaccount` to manage multiple AWS accounts using the same CLI|
  |---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
* |`aws s3 ls`      |Lists the contents of an S3 bucket (default profile)|
  |-----------      |----------------------------------------------------|
* |`aws s3 ls --profile IAMADMIN-Generalaccount`|Lists the contents of an S3 bucket using the credentials configured for the `IAMADMIN-Generalaccount` profile|
  |---------------------------------------------|-------------------------------------------------------------------------------------------------------------|








