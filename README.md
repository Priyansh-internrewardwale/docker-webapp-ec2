# Dockerized Web App on AWS EC2

## Objective

This project demonstrates how to Dockerize a simple Node.js app and deploy it on an AWS EC2 instance using Docker.

## Technologies Used

- Docker
- AWS EC2 (Amazon Linux)
- Git + GitHub

## Run Locally with Docker

1. Clone the repo:
   git clone https://github.com/Priyansh-internrewardwale/docker-webapp-ec2.git
   cd docker-webapp-ec2

2. Build the Docker image:
   docker build -t webapp .

3. Run the app:
   docker run -p 3000:3000 webapp

4. Open in browser:
   http://localhost:3000

## Deploy on AWS EC2

1. Launch EC2 Instance:

   - AMI: Amazon Linux
   - Instance Type: t2.micro
   - Key Pair: ec2-key.pem
   - Inbound Rules:
     - Port 22 (SSH) from My IP
     - Port 3000 (Custom TCP) from 0.0.0.0/0

2. Connect via SSH:
   ssh -i /path/to/ec2-key.pem ec2-user@3.82.235.40:3000

3. Install Docker:
   sudo dnf update -y
   sudo dnf install docker -y
   sudo systemctl start docker
   sudo systemctl enable docker
   sudo usermod -aG docker ec2-user
   exit

4. Reconnect and set up the app:
   ssh -i /path/to/ec2-key.pem ec2-user@3.82.235.40:3000
   git clone https://github.com/Priyansh-internrewardwale/docker-webapp-ec2.git
   cd docker-webapp-ec2
   docker build -t webapp .
   docker run -d -p 3000:3000 webapp

5. Open in browser:
   http://3.82.235.40:3000:3000

## Screenshots (Google Drive)

- Docker running locally:

1. [View]https://drive.google.com/file/d/1FM_LI9r7z67t6qgDTx_bJjTWvfmirHOI/view?usp=drive_link
2. [View]https://drive.google.com/file/d/1Jpiy2ZHEtJIOxC1d0GUV0Y6wVuXZX_DE/view?usp=drive_link

- EC2 Dashboard:

1. [View]https://drive.google.com/file/d/1x16hnWgH8WYaP5KFmw_FdPgsBSrQcj9Y/view?usp=drive_link
2. [View]https://drive.google.com/file/d/1_-rsx4yfMFnIpuLtveDAoiFXKxh44dqG/view?usp=drive_link

- SSH Terminal Session: [View]https://drive.google.com/file/d/1PBGH6kafyzkhnWGBIX3Ca6iEbh_ePBCf/view?usp=drive_link
- App running on EC2 via IP: [View]https://drive.google.com/file/d/1Lia1yLC1djqkSS8lP6VJoosC0Uv1G5ZD/view?usp=drive_link

## Project Links

- GitHub Repo: https://github.com/Priyansh-internrewardwale/docker-webapp-ec2
- Google Drive Folder: https://drive.google.com/drive/folders/19quWXiltjVscpb-CzdJ3pzA6xtwiF_Kc
