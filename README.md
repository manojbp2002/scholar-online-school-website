
# Scholar - Online School Website

## Project Overview
This project involves the deployment of a static educational website using an Apache server hosted on an AWS EC2 instance. The website, based on the "Scholar" HTML5 template, is designed for online educational platforms. It features multiple sections including services, courses, testimonials, and contact information.

## Features
- **Responsive Design**: The website is fully responsive, adapting to different screen sizes for an optimal viewing experience.
- **Educational Content**: Sections for online courses, team members, and upcoming events.
- **Interactive Elements**: Includes a preloader, carousels, and an accordion for a dynamic user experience.
- **Bootstrap Framework**: Built using Bootstrap for a modern and flexible design.
- **Cross-Browser Compatibility**: The website works well across different web browsers.

## Technologies Used
- **AWS EC2**: Virtual server hosting in the cloud.
- **Apache HTTP Server**: Web server software used to serve the website.
- **HTML5/CSS3**: Core technologies used to structure and style the web pages.
- **JavaScript**: Used for interactive elements like carousels and accordions.
- **Bootstrap**: A front-end framework for building responsive websites.
  

## Setup Instructions

### 1. Launch an EC2 Instance
1. Sign in to your AWS Management Console.
2. Navigate to the **EC2 Dashboard**.
3. Click on **Launch Instance**.
4. Choose **Amazon Linux 2** as the AMI.
5. Select an instance type (e.g., t2.micro for free tier eligibility).
6. Configure instance details and proceed with the default settings.
7. Add storage (default is 8 GB, which is sufficient).
8. Configure the security group to allow HTTP (port 80) and SSH (port 22) traffic.
9. Review and launch the instance, creating or using an existing key pair for SSH access.

### 2. Connect to the EC2 Instance
1. Open a terminal or command prompt on your local machine.
2. Use SSH to connect to the EC2 instance
3. Make sure git is installed on the ec2 instance.

### 3. Install Apache HTTP Server
1. Update the instance’s package manager:
   ```
   sudo yum update -y
   ```
2. Install Apache:
   ```
   sudo yum install httpd -y
   ```
3. Start the Apache service:
   ```
   sudo systemctl start httpd
   ```
4. Enable Apache to start on boot:
   ```
   sudo systemctl enable httpd
   ```

### 4. Deploy the Website
1. clone the repository consisting of website files (including `index.html`, CSS, JS, and image assets) to the EC2 instance using git:
   ```
   git clone <remote_reository_url>
   ```
3. Move the website files to the Apache server's root directory:
   ```
   sudo cp index.html /var/www/html/
   sudo cp  assets /var/www/html/
   ```
4. Restart the apache service:
   ```
   sudo systemctl restart httpd
   ``` 
5. Verify the deployment by visiting the public IP of your EC2 instance in a web browser:
   ```
   http://your-ec2-public-ip
   ```

## Usage
- The website is accessible via the public IP address of your EC2 instance.
- Customize the content by editing the HTML, CSS, and JavaScript files in the `/var/www/html/` directory.

## Future Enhancements
- Implement SSL/TLS to secure the website using HTTPS.
- Add dynamic content using a back-end service or CMS.
- Integrate a Continuous Integration/Continuous Deployment (CI/CD) pipeline for automated updates.
