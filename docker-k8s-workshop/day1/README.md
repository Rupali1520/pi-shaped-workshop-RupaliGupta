# Docker Day 1 Exercise – Hello Docker App

## Overview
This project is a simple Flask-based "Hello, World!" REST API, containerized using Docker.

## How to Run

```bash
git clone <URL>
cd <repo-name>
docker build -t <image-name>:day1 .
docker run -p 8080:8080 <image-name>:day1


## 📘 Core Concept Questions

### 1. Why is Docker useful in building and deploying microservices?

Docker enables microservices by packaging each service with its dependencies, ensuring consistency across environments. It simplifies CI/CD, enhances scalability, and allows independent updates and deployments in complex systems like e-commerce or banking apps.

---

### 2. What is the difference between a Docker image and a container?

A Docker image is a blueprint or snapshot of your application and its environment. A container is a running instance of that image. You scale by creating multiple containers from the same image.

---

### 3. How does Kubernetes complement Docker at scale?

Kubernetes automates container orchestration—scheduling, scaling, load balancing, and self-healing. For example, running hundreds of containers in production becomes manageable and resilient using Kubernetes.



