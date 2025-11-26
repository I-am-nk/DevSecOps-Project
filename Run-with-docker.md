# 🚀 How to run this application with the help of Docker 
---

## 📥 1. Clone This Repository

```
git clone https://github.com/I-am-nk/DevSecOps-Project.git
```

## 📥 2.Move into the directory:
```
cd DevSecOps-Project
```

## 🐳 3. Build the Docker Image

Before building, make sure Docker is installed.

🔧 Replace <dockerhub-username> with your own Docker Hub ID

✅ Build Command:

```
docker build -t <dockerhub-username>/devsecops-project:v1 .
```

## ▶️ 4. Run the Docker Container Locally

The container uses NGINX, which exposes port 80 internally.
Map it to any free port on your local machine — commonly 8080.

```
docker run -d -p 8080:80 --name devsecops-app <dockerhub-username>/devsecops-project:v1
```

## 🌐 4. Access the Application Locally

Open any browser and visit:

```
http://localhost:8080
```

You should now see the running application.

## 📑 5. Project Dockerfile Overview

This project uses a multi-stage Dockerfile:

Stage 1 – Build the Frontend

Uses Node.js (20-alpine)

Installs dependencies using npm ci

Builds the production bundle

Stage 2 – Serve via NGINX

Uses nginx:alpine

Copies frontend build output into NGINX html directory

Exposes port 80

Runs NGINX in foreground

This results in:
✔ Smaller image
✔ Faster runtime
✔ Cleaner production builds