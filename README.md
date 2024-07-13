
#### Dockerized Flask Application Deployment on AWS EC2

#### Overview
This project demonstrates the deployment of a Dockerized Flask-based User Management application on AWS EC2. It includes instructions for setting up Docker, pulling the Docker image, and running the application.

#### Technologies Used
- Flask
- Docker
- AWS EC2

#### Prerequisites
1. AWS Account with access to EC2.
2. Basic knowledge of AWS services, Docker, and command line interface.

#### Steps to Deploy on AWS EC2

#### 1. Connect to Your EC2 Instance via SSH

1. **Open Terminal (or Command Prompt)**

2. **SSH into EC2 Instance**
   ```bash
   ssh -i /path/to/your-key.pem ec2-user@<EC2-Public-IP>
   ```
   Replace `/path/to/your-key.pem` with the path to your private key file and `<EC2-Public-IP>` with your instance's public IP address.

3. **Update the System**
   ```bash
   sudo yum update -y
   ```

#### 2. Install Docker on EC2 Instance

1. **Install Docker**
   ```bash
   sudo yum install docker
   ```

2. **Start Docker Service**
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   ```
3. **Check Docker Service Status**
   ```bash
   sudo systemctl status docker
   ```
4. **Verify Docker Installation**
   ```bash
   docker --version
   ```

#### 3. Pull and Run Docker Image

1. **Pull Docker Image**
   ```bash
   sudo docker pull jagruti03shinde/user-management-application:01
   ```

2. **Run Docker Container**
   ```bash
   sudo docker run -d -p 80:5000 jagruti03shinde/user-management-application:01
   ```

3. **Access the Application**
   - Open a web browser and navigate to:
     ```
     http://<EC2-Public-IP>
     ```
     Replace `<EC2-Public-IP>` with your actual EC2 instance's public IP address.

#### Additional Notes
- Ensure your security group allows inbound traffic on port `80` or your configured port.
- Customize the application settings and environment variables as needed.

## Admin Credentials

Use the following credentials to log in to the admin portal:

- **Email:** `admin@gmail.com`
- **Password:** `admin@123`

#### Author
Jagruti D. Shinde
