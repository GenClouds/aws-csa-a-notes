To send emails using a dedicated IP with Amazon SES via PHP, you'll need to set up your email headers correctly. The envelope-from address (or Return-Path) is particularly important when using a dedicated IP, as it determines which IP is used for sending.

###  Preparing php environment :
# Install AWS SDK for PHP

To install the AWS SDK for PHP, use Composer with the following command:

```bash
composer require aws/aws-sdk-php
```
# install PHPMailer
you can set up the envelope header in PHP using the mail() function or an external library like PHPMailer
```bash
composer require phpmailer/phpmailer

```
# Set Up the PHPMailer Code:
Here’s an way of how to configure PHPMailer to use a dedicated IP:
here is the code 

```bash
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\Exception;

require 'vendor/autoload.php';

$mail = new PHPMailer(true);
try {
    // Server settings
    $mail->isSMTP();
    $mail->Host = 'email-smtp.us-east-1.amazonaws.com'; // Your SMTP server
    $mail->SMTPAuth = true;
    $mail->Username = 'your-smtp-username'; // SMTP username
    $mail->Password = 'your-smtp-password'; // SMTP password
    $mail->SMTPSecure = 'tls'; // Enable TLS encryption
    $mail->Port = 587; // TCP port to connect to

    // Set the envelope sender (this sets the dedicated IP)
    $mail->setFrom('your-email@yourdomain.com', 'Your Name'); // From email
    $mail->addReplyTo('your-email@yourdomain.com', 'Your Name');

    // Set the Return-Path (Envelope Sender)
    $mail->addCustomHeader('X-SES-Return-Path', 'your-email@yourdomain.com'); // Dedicated IP email

    // Recipients
    $mail->addAddress('recipient@example.com', 'Recipient Name');

    // Content
    $mail->isHTML(true);
    $mail->Subject = 'Test Email';
    $mail->Body    = 'This is a test email sent using Amazon SES with a dedicated IP!';
    
    $mail->send();
    echo 'Message has been sent';
} catch (Exception $e) {
    echo "Message could not be sent. Mailer Error: {$mail->ErrorInfo}";
}
```
# Using PHP's mail() Function
If you're using PHP's built-in mail() function, you cannot set the envelope sender directly through headers in the same way as PHPMailer. You typically specify the return path as an additional parameter in the mail() function:
```bash
$to = 'recipient@example.com';
$subject = 'Test Email';
$message = 'This is a test email sent using Amazon SES with a dedicated IP!';
$headers = "From: your-email@yourdomain.com\r\n";
$headers .= "Reply-To: your-email@yourdomain.com\r\n";
$headers .= "X-SES-Return-Path: your-email@yourdomain.com\r\n";

mail($to, $subject, $message, $headers);
```
