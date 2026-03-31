**🚀 DevSecOps Pipeline for Flask Application**

This repository demonstrates a complete end-to-end DevSecOps pipeline built for a Python Flask application. The project focuses on integrating security practices at every stage of the CI/CD lifecycle, from code quality checks to deployment on AWS EC2.

**📌 Project Overview**

This project was built as a hands-on exercise to understand real-world DevSecOps practices. It includes automated workflows for:

Code quality analysis
Security scanning
Containerization
Continuous Integration & Continuous Deployment (CI/CD)
Cloud deployment

**🛠️ Tech Stack**
**Backend:** Python (Flask)
**CI/CD:** GitHub Actions
**Containerization:** Docker
**Cloud:** AWS EC2
**Web Server:** Gunicorn

**🔐 DevSecOps Pipeline Stages**

1. Code Quality & Linting
   Uses flake8 to ensure code quality and detect potential issues.
2. Security & Dependency Checks
   Scans dependencies for known vulnerabilities.
3. Dockerfile Linting
   Uses Hadolint to enforce best practices in Dockerfile.
4. Build & Push Docker Image
   Builds Docker image and pushes it to Docker Hub.
5. Container Image Scanning
   Uses Trivy to scan Docker images for vulnerabilities.
6. Deployment
   Automatically deploys the application to AWS EC2.
   Uses Gunicorn as the application server.

**⚙️ CI/CD Workflow**

The pipeline is fully automated using GitHub Actions:

Code push triggers the workflow
Runs linting and security checks
Builds Docker image
Scans image for vulnerabilities
Pushes image to Docker Hub
Deploys application to EC2 instance

**🔑 Environment Variables**

Make sure to configure the following secrets in your GitHub repository:

DOCKER_USERNAME
DOCKER_PASSWORD
AWS_EC2_HOST
AWS_EC2_USER
AWS_SSH_KEY

**🚀 How to Run Locally**
# Clone the repository
git clone https://github.com/Pratikprajapati20/github-actions-practice.git


# Navigate to project directory
cd github-actions-practice


# Build Docker image
docker build -t flask-devsecops .


# Run container
docker run -p 5000:5000 flask-devsecops

**📊 Key Learnings**
Security should be integrated at every stage of the pipeline
Managing environment variables securely is crucial
CI/CD pipelines require proper permission handling
Automated deployments improve consistency and reliability

**🙏 Acknowledgment**

Special thanks to my mentor Shubham Londhe for guidance and support throughout this project.

⭐ If you found this project helpful, don’t forget to give it a star!
