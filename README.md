# MainCrafts-Project-02-Task
# Containerization Using Docker and Deployment on AWS EC2

## 📌 Project Overview

This project demonstrates how to containerize a static portfolio website using **Docker** and deploy it on a **cloud virtual machine (AWS EC2)**.

The goal of this task was to understand the basics of **containerization, Docker images, containers, and cloud deployment** while hosting a website accessible through a public IP address.

This task was completed as part of my **DevOps Internship at Maincrafts Technology**.

---

## 🚀 Technologies Used

* Docker
* AWS EC2 (Ubuntu)
* Nginx
* HTML
* CSS
* Linux Commands
* Git & GitHub

---

## 🧠 Concepts Learned

* Containerization
* Docker Images and Containers
* Dockerfile creation
* Running containers on a cloud VM
* Deploying web applications using Docker
* Accessing applications via EC2 public IP



## 📂 Project Structure

portfolio-docker-deployment/
│
├── index.html
├── style.css
├── Dockerfile
└── README.md


## ⚙️ Step 1: Launch an AWS EC2 Instance

1. Go to AWS Console
2. Launch an **Ubuntu EC2 instance**
3. Configure security group:

   * Allow **HTTP (Port 80)**
   * Allow **SSH (Port 22)**

Connect to the instance:

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

---

## ⚙️ Step 2: Install Docker on EC2

Update packages:

```bash
sudo apt update
```

Install Docker:

```bash
sudo apt install docker.io -y
```

Start Docker service:

```bash
sudo systemctl start docker
```

Enable Docker on boot:

```bash
sudo systemctl enable docker
```

Check Docker version:

```bash
docker --version
```

---

## ⚙️ Step 3: Create Dockerfile

Create a Dockerfile in your project folder.

```dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html
```

This Dockerfile:

* Uses **Nginx base image**
* Copies website files into the Nginx web directory.

---

## ⚙️ Step 4: Build Docker Image

Navigate to the project directory and run:

```bash
docker build -t portfolio-website .
```

Check available images:

```bash
docker images
```

---

## ⚙️ Step 5: Run Docker Container

Run the container and expose port 80:

```bash
docker run -d -p 80:80 portfolio-website
```

Check running containers:

```bash
docker ps
```

---

## 🌐 Step 6: Access the Website

Open your browser and enter:

```
http://your-ec2-public-ip
```

Your **portfolio website should now be live using Docker on AWS EC2**.

---

## 📸 Output

The deployed portfolio website is accessible through the **EC2 public IP address** and served using **Nginx inside a Docker container**.

---

## 🎯 Key Learning Outcomes

* Understanding Docker containerization
* Creating Docker images using Dockerfile
* Deploying applications on cloud virtual machines
* Running web servers inside containers
* Managing containers using Docker commands

---

## 👨‍💻 Author

**Manish Kumar**
DevOps Intern – Maincrafts Technology

