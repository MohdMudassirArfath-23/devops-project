# AWS DevOps CI/CD Pipeline with Jenkins

## Project Overview

This project demonstrates an end-to-end CI/CD pipeline for deploying a web application on AWS.

The project uses Jenkins for automation, Docker for containerization, Amazon ECR for container image storage, and Amazon EC2 for application deployment.

## Technologies Used

- AWS EC2
- AWS ECR
- Jenkins
- Docker
- Git
- GitHub
- Linux
- Nginx

## Architecture

GitHub
   ↓
Jenkins
   ↓
Docker Build
   ↓
Amazon ECR
   ↓
Amazon EC2
   ↓
Web Application

## Project Workflow

1. Developer pushes application code to GitHub.
2. Jenkins pulls the source code.
3. Jenkins builds the Docker image.
4. Docker image is tagged with the required version.
5. Docker image is pushed to Amazon ECR.
6. EC2 pulls the Docker image from ECR.
7. Docker container is started on EC2.
8. The web application is accessed through the EC2 public IP.

## Project Files

- index.html - Web application
- Dockerfile - Docker image configuration
- Jenkinsfile - Jenkins CI/CD pipeline
- README.md - Project documentation

## AWS Services

### EC2
Used to host and run the containerized application.

### ECR
Used to store Docker container images.

### IAM
Used to provide required AWS permissions.

### Security Groups
Used to control network access to the EC2 instance.

## Result

The web application is successfully containerized using Docker and deployed on AWS EC2 through a Jenkins CI/CD pipeline.

## Author

Mohd Mudassir Arfath
