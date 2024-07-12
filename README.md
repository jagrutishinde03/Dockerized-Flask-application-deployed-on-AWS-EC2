#### Dockerized Flask Application Deployment on AWS EC2

#### Overview
This project demonstrates the deployment of a Dockerized Flask-based User Management application on AWS EC2. It includes instructions for setting up the EC2 instance, installing Docker, pulling the Docker image, and running the application.

#### Technologies Used
- Flask
- Docker
- AWS EC2

#### Prerequisites
1. AWS Account with access to EC2.
2. Basic knowledge of AWS services, Docker, and command line interface.

#### Steps to Deploy on AWS EC2

#### 1. Launch an EC2 Instance

1. **Sign in to AWS Console**
   - Go to [AWS Management Console](https://aws.amazon.com/console/) and sign in.

2. **Launch Instance**
   - Navigate to EC2 service.
   - Click on "Launch Instance" to create a new instance.

3. **Choose an Amazon Machine Image (AMI)**
   - Select an Ubuntu or Amazon Linux AMI.

4. **Choose Instance Type**
   - Select an instance type based on your application requirements.

5. **Configure Instance Details**
   - Configure instance details such as network, subnet, and IAM role.

6. **Add Storage**
   - Add storage as per your application's storage requirements.

7. **Add Tags (Optional)**
   - Add tags for better identification.

8. **Configure Security Group**
   - Create or select an existing security group.
   - Add a rule to allow inbound traffic on port `80` (HTTP) or your configured port.

9. **Review and Launch**
   - Review the instance details and click "Launch".
   - Select or create a new key pair to connect to your instance securely.

10. **Access the Instance**
    - Once launched, note down the public IP address or DNS name of your EC2 instance.

#### 2. Connect to EC2 Instance via SSH

1. **Open Terminal (or Command Prompt)**

2. **SSH into EC2 Instance**
   ```bash
   ssh -i /path/to/your-key.pem ubuntu@<EC2-Public-IP>
   ```
   Replace `/path/to/your-key.pem` with the path to your private key file and `<EC2-Public-IP>` with your instance's public IP address.

3. **Update the System**
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```

#### 3. Install Docker on EC2 Instance

1. **Install Docker**
   ```bash
   sudo yum install docker
   ```

2. **Start Docker Service**
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   ```

3. **Verify Docker Installation**
   ```bash
   docker --version
   ```

#### 4. Pull and Run Docker Image

1. **Pull Docker Image**
   ```bash
   docker pull jagruti03shinde/user-management-application:01
   ```

2. **Run Docker Container**
   ```bash
   docker run -d -p 80:5000 jagruti03shinde/user-management-application:01
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

#### License
Include license information if applicable.

#### Author
Your name or organization.
