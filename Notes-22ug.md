##### A user data script for launching an employee directory application on an EC2 instance running Amazon Linux. 





```bash
#!/bin/bash
# Update the package repository
yum update -y

# Install necessary packages
yum install -y httpd git

# Start the Apache web server
systemctl start httpd
systemctl enable httpd

# Clone the employee directory application from GitHub
git clone https://github.com/your-repo/employee-directory.git /var/www/html/employee-directory

# Change directory to the application folder
cd /var/www/html/employee-directory

# Install application dependencies (assuming a Node.js application)
curl -sL https://rpm.nodesource.com/setup_14.x | bash -
yum install -y nodejs
npm install

# Start the application (assuming it uses a process manager like PM2)
npm install -g pm2
pm2 start app.js
pm2 startup systemd
pm2 save

# Open port 80 in the security group to allow HTTP traffic
aws ec2 authorize-security-group-ingress --group-id sg-xxxxxxxx --protocol tcp --port 80 --cidr 0.0.0.0/0
