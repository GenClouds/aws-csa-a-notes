# Amazon Simple Email Service (SES)

Amazon Simple Email Service (SES) is a cloud-based email service designed to help you send and receive emails at scale. A cost-effective way to send marketing, transactional, and notification emails using your own email addresses and domains. SES can be integrate with other AWS services, making it easy to add email-sending capabilities to  our applications.
## How SES Works

### Email Sending
You can send emails using the SES API, SMTP interface, or by integrating with other AWS services like Amazon SNS (Simple Notification Service) and AWS Lambda.

### Email Receiving
SES can also receive emails, allowing you to develop solutions like autoresponders, unsubscribe systems, and customer support ticket generators.

### Email Authentication
SES supports DKIM (DomainKeys Identified Mail) to help authenticate your emails and improve deliverability.

### Monitoring and Reporting
SES provides detailed reports on email sending activities, including delivery rates, bounces, and complaints.

# SES Dedicated and Standard IPs

## Definition
- **DEDICATED**: Only for you; you are the only one using the IP to send mail.
- **STANDARD**: You manage it.
- **MANAGED**: AWS manages it.
- **SES (Simple Email Service)**: A service for sending mail over SMTP.

When choosing IP addresses for sending emails in SES, there are two main options: 

### SES Dedicated Managed IP
**Explanation**: AWS manages the dedicated IP addresses. AWS is responsible for IP warmup, ensuring emails are not marked as spam, and improving deliverability.
- **Pros**: Less admin overhead, better deliverability.
- **Cons**: Higher cost.

**Details**:
- AWS takes care of IP warmup.
- AWS handles reputation monitoring and follows best practices for email durability.
- Ideal for high-volume email sends but more cost-effective for larger operations.

### SES Dedicated Standard IP
**Explanation**: You manage the dedicated IP addresses. You are responsible for IP warmup, ensuring deliverability, and avoiding spam marking.
- **Pros**: More control.
- **Cons**: More work on your part.

**Details**:
- More control over IP usage, allowing decisions on how and when to send emails.
- IP warmup required manually: start with a low volume of emails and gradually increase the volume.

