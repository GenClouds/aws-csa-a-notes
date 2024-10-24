### Step 1: Create an Amazon SES Account

1. **Sign up for AWS**:  sign up at [AWS](https://aws.amazon.com/).
2. **Verify Your Domain or Email**: In the SES console, verify the domain or email addresses you'll be using to send emails. This is necessary for SES to allow you to send emails.after verifying go  for any application/host to which we need to configure SMTP . provided the verified details username ,password, SMTP host and alll required and saved

### Step 2: Choose Between IP Options

- **Dedicated Managed IPs**: These are IP addresses that are assigned specifically to you. They offer better control over your sending reputation but may come at an additional cost.
- **Standard IPs**: These are shared IP addresses used by multiple AWS customers. They are suitable for most users and have lower costs.

**Recommendation**: If you expect to send a high volume of emails or need specific IP reputation management, go for dedicated managed IPs. For lower volumes, standard IPs are generally sufficient.

### Step 3: Set Up Your PHP Environment

1. **Install AWS SDK for PHP**:
   You can use Composer to install the AWS SDK:

   ```bash
   composer require aws/aws-sdk-php
   ```

2. **Send Email Using SES**:
   Use the following PHP code to send an email and check envelope headers:

   ```php
   <?php
   require 'vendor/autoload.php';

   use Aws\Ses\SesClient;
   use Aws\Exception\AwsException;

   // Create an AWS SES client
   $client = new SesClient([
       'version' => 'latest',
       'region' => 'us-east-1', // Change to your desired region
       'credentials' => [
           'key'    => 'YOUR_AWS_ACCESS_KEY_ID',
           'secret' => 'YOUR_AWS_SECRET_ACCESS_KEY',
       ],
   ]);

   $senderEmail = 'your-verified-email@example.com';
   $recipientEmail = 'recipient@example.com';

   $subject = 'Test Email from SES';
   $plaintextBody = 'This is a test email sent using Amazon SES.';
   $htmlBody = '<h1>Test Email</h1><p>This is a test email sent using Amazon SES.</p>';

   $message = [
       'Source' => $senderEmail,
       'Destination' => [
           'ToAddresses' => [$recipientEmail],
       ],
       'Message' => [
           'Subject' => [
               'Data' => $subject,
           ],
           'Body' => [
               'Text' => [
                   'Data' => $plaintextBody,
               ],
               'Html' => [
                   'Data' => $htmlBody,
               ],
           ],
       ],
   ];

   // Send the email
   try {
       $result = $client->sendEmail($message);
       echo 'Email sent! Message ID: ' . $result['MessageId'] . "\n";
   } catch (AwsException $e) {
       echo 'Error: ' . $e->getMessage() . "\n";
   }
   ```

### Step 4: Check Envelope Headers

When you receive the email, you can check the envelope headers as described in the previous response. If you're fetching emails via IMAP, you'd use the `imap` functions to retrieve the headers. as by following code 

# Fetching Email Headers with IMAP

Enable the IMAP extension in your PHP installation if it's not already enabled.

Use the following code to connect to your IMAP server and fetch the headers:

```php
<?php
// Connect to the IMAP server
$mailbox = '{imap.example.com:993/imap/ssl}INBOX'; // Replace with your mailbox settings
$username = 'your-email@example.com'; // Your email
$password = 'your-password'; // Your password

// Open an IMAP stream
$inbox = imap_open($mailbox, $username, $password) or die('Cannot connect: ' . imap_last_error());

// Get the number of messages
$numMessages = imap_num_msg($inbox);

// Loop through the messages
for ($i = 1; $i <= $numMessages; $i++) {
    // Fetch the headers of each message
    $header = imap_headerinfo($inbox, $i);
    
    // Display the envelope header
    echo "Subject: " . $header->subject . "<br>";
    echo "From: " . $header->from[0]->mailbox . "@" . $header->from[0]->host . "<br>";
    echo "To: " . $header->to[0]->mailbox . "@" . $header->to[0]->host . "<br>";
    echo "Date: " . $header->date . "<br><br>";
}

// Close the IMAP stream
imap_close($inbox);
?>

Important Notes:
Replace imap.example.com, your email, and password with your actual email service details.
Make sure your server allows IMAP connections.
Be cautious about handling passwords and sensitive information.
```
#### Important Notes

- Ensure that your AWS credentials have the necessary permissions for SES.
- Replace placeholders in the code with your actual AWS keys and email addresses.
- Monitor your sending limits and adhere to AWS SES policies to maintain your account's good standing.
