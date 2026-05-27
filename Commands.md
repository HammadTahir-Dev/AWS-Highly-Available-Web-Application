# AWS Highly Available Web Application Commands
## Connect to EC2 Instances
ssh -i "HA-keypair.pem" ec2-user@PUBLIC-IP

# Update Server
sudo yum update -y

# Install Apache Web Server
sudo yum install httpd -y

# Start Apache Service
sudo systemctl start httpd
sudo systemctl enable httpd

# Check Apache Status
sudo systemctl status httpd

# Create Web Page for AZ1
sudo tee /var/www/html/index.html > /dev/null <<EOF
<!DOCTYPE html>
<html>
<head>
<title>AZ1 Server</title>
</head>
<body>
<h1>Highly Available AWS Application</h1>
<h2>Server Running from AZ1</h2>
<p>Developed by Muhammad Hammad</p>
</body>
</html>

# Create Web Page for AZ2
sudo tee /var/www/html/index.html > /dev/null <<EOF
<!DOCTYPE html>
<html>
<head>
<title>AZ2 Server</title>
</head>
<body>
<h1>Highly Available AWS Application</h1>
<h2>Server Running from AZ2</h2>
<p>Developed by Muhammad Hammad</p>
</body>
</html>

# Restart Apache
sudo systemctl restart httpd

# Verify Website
Open browser:
http://LOAD-BALANCER-DNS

# Test High Availability
## Stop One EC2 Instance
AWS Console:
- EC2
- Select instance
- Instance State
- Stop Instance

# Verify Fault Tolerance

Refresh ALB DNS page.

Expected Result:
- Website remains accessible
- Traffic redirects to healthy instance

# Security Group Rules
## Inbound Rules

| Type | Port | Source |
|------|------|---------|
| SSH | 22 | My IP |
| HTTP | 80 | 0.0.0.0/0 |

# Outbound Rules

| Type | Destination |
|------|-------------|
| All Traffic | 0.0.0.0/0 |

# Route Table Rule

| Destination | Target |
|-------------|--------|
| 0.0.0.0/0 | Internet Gateway |

# AWS Components Used

- Amazon VPC
- Public Subnets
- Internet Gateway
- Route Tables
- Security Groups
- EC2 Instances
- Apache Web Server
- Application Load Balancer
- Target Group