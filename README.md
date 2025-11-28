# 🚀 Discover Dollar — Full DevOps Assignment

## CI/CD | Docker | GitHub Actions | AWS EC2 | Nginx | MongoDB

This project contains the complete DevOps workflow for deploying a full-stack CRUD application using:

Docker (Backend + Frontend + MongoDB)

GitHub Actions CI/CD

AWS EC2 Ubuntu Instance

Docker Hub Registry

Nginx Reverse Proxy for Frontend

docker-compose for multi-container orchestration

This README includes step-by-step setup, deployment instructions, and screenshot placeholders as required in the assignment.

## 🌟 Features Implemented
✔️ Dockerized Frontend & Backend

Backend (Node.js + Express)

Frontend (Angular served from Nginx)

MongoDB running inside Docker

docker-compose to run everything together

✔️ Automated CI/CD Pipeline (GitHub Actions)

Auto-build Docker images

Auto-push to Docker Hub

Auto-SSH into EC2

Auto-deploy using docker-compose

Zero-downtime production updates

✔️ AWS EC2 Deployment (Ubuntu 22.04)

Pulls Docker images from Docker Hub

Runs full application stack using docker-compose

Production ready & stable

## 🏗️ Architecture
Developer Push Code

        │
        ▼
        
GitHub → GitHub Actions CI/CD → Build Docker Images → Push to Docker Hub

        │
        ▼
        
 AWS EC2 pulls new images via SSH → docker-compose up -d → Deploy

## 🛠️ LOCAL SETUP
### 1️⃣ Clone Repository
git clone https://github.com/harshita194/Discover-Dollar-Assignment-.git

cd Discover-Dollar-Assignment-

### 2️⃣ Build Docker Images
docker build -t mean_backend -f DockerFile_Backend .

docker build -t mean_nginx -f DockerFile_nginx .

### 3️⃣ Run Full Stack Locally
docker compose up -d

### ☁️ AWS EC2 SETUP (PRODUCTION)
### 4️⃣ SSH into EC2
ssh -i "docker-key.pem" ubuntu@YOUR_EC2_PUBLIC_IP

### 5️⃣ Install Docker
sudo apt update

curl -fsSL https://get.docker.com | sudo sh

### 6️⃣ Install Docker Compose
sudo apt install docker-compose -y

### 7️⃣ Clone Repo in EC2
git clone https://github.com/harshita194/Discover-Dollar-Assignment-.git

cd Discover-Dollar-Assignment-

### 8️⃣ Run App on EC2
docker compose up -d


Your full application is now deployed on EC2.

## 🔐 GitHub Secrets Used

Secret Name	Description

DOCKERHUB_USERNAME	Your Docker Hub username

DOCKERHUB_TOKEN	Docker Hub access token

EC2_HOST	EC2 public IP (e.g., 13.126.230.98)

EC2_SSH_KEY	Entire content of docker-key.pem


## ⚙️ CI/CD PIPELINE (GitHub Actions Workflow)

File: .github/workflows/ci-cd.yml

This pipeline:

✔ Builds backend Docker image

✔ Builds frontend (Angular) Nginx image

✔ Pushes both images to Docker Hub

✔ SSH into EC2

✔ Pulls new images

✔ Restarts containers with docker compose up -d

✔ Removes old images

Everything is automated when you push to main branch.


## 1️⃣ CI/CD Pipeline Execution

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 4 47 13 PM" src="https://github.com/user-attachments/assets/2cad77bd-a47a-4d27-856f-171e012f4c93" />


## 2️⃣ Docker Image Build & Push

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 2 54 01 AM" src="https://github.com/user-attachments/assets/3a7c51e9-13c5-4286-848e-a9ed36470e62" />

<img width="1423" height="899" alt="Screenshot 2025-11-28 at 5 16 39 PM" src="https://github.com/user-attachments/assets/4205471b-8fc7-4d1a-a763-a55f802c835e" />


## 3️⃣ EC2 Deployment 

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 3 01 36 PM" src="https://github.com/user-attachments/assets/3b42fe00-aa34-40c5-9404-87ff471bb1d5" />


## 4️⃣ Working Application UI

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 2 51 02 PM" src="https://github.com/user-attachments/assets/d0d5082b-ca8e-467c-bc20-75d80e94d249" />

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 2 53 07 PM" src="https://github.com/user-attachments/assets/5f97a11e-6396-4d1e-9264-63b9a7c93d2d" />

<img width="1440" height="900" alt="Screenshot 2025-11-28 at 2 55 39 PM" src="https://github.com/user-attachments/assets/39debaa5-8f8c-4b0c-bdca-f4d9dec96c9d" />


##🌐 Accessing the Deployed App

### Once deployed, open:

http://YOUR_EC2_PUBLIC_IP/

Example:

http://13.126.230.98/

### 🧪 Testing API (Optional)
curl http://YOUR_EC2_PUBLIC_IP/api/users

### 🧹 Useful Docker Commands
Stop all containers
docker compose down

### Remove old images
docker image prune -f

### View logs
docker logs container-name

