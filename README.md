# DevOps Capstone Project – End-to-End CI/CD Pipeline for a Node.js Web Application

## Project Overview

This project demonstrates an end-to-end DevOps pipeline for deploying a Node.js web application using GitHub, Jenkins, Docker, AWS EC2, Prometheus, Grafana, Shell Scripting, and Cron Jobs.

The project automates the complete software delivery process from source code management to deployment and infrastructure monitoring.

---

## Architecture Flow

1. Developer pushes code to GitHub.
2. Jenkins automatically triggers the pipeline.
3. Jenkins builds the Docker image.
4. Docker image is pushed to Docker Hub.
5. Docker container is deployed on the AWS EC2 application server.
6. Prometheus collects metrics from Node Exporter.
7. Grafana visualizes metrics and generates alerts.
8. Cron jobs automate backup and cleanup tasks.
   
Cron Jobs are used to automate backup and cleanup tasks.

---

## Technology Stack

* Git & GitHub
* Jenkins
* Node.js
* Docker
* Docker Hub
* AWS EC2 (Ubuntu)
* Prometheus
* Grafana
* Node Exporter
* Bash Shell Scripting
* Cron Jobs

---

## Project Structure

```
Capstone_Project/
│── app.js
│── package.json
│── package-lock.json
│── Dockerfile
│── Jenkinsfile
│── README.md
```

---

## Setup Instructions

### Clone Repository

```bash
git clone https://github.com/TAMILSELVANMANOHAR/Capstone_Project.git
```

### Install Dependencies

```bash
npm install
```

### Run Application

```bash
node app.js
```

The application runs on:

```
http://localhost:3000
```

---

## Docker Commands

Build Docker Image

```bash
docker build -t capstone-app .
```

Run Docker Container

```bash
docker run -d -p 3000:3000 capstone-app
```

---

## Jenkins Pipeline

The Jenkins pipeline performs the following tasks:

1. Clone source code from GitHub
2. Install Node.js dependencies
3. Build Docker image
4. Push Docker image
5. Deploy application on AWS EC2

---

## Monitoring

Infrastructure monitoring is implemented using:

* Prometheus
* Node Exporter
* Grafana Dashboard

The dashboard monitors:

* CPU Usage
* Memory Usage
* Disk Usage
* Network Receive
* Network Transmit

Grafana alerting is configured for:

* CPU Usage greater than 80% for 5 minutes

---

## Shell Scripts

### backup.sh

Creates a compressed backup of the application.

### cleanup.sh

Deletes backup files older than seven days.

---

## Cron Jobs

```cron
0 2 * * * /home/ubuntu/backup.sh
0 3 * * * /home/ubuntu/cleanup.sh
```

---

## Project Outcome

This project successfully demonstrates a complete DevOps CI/CD pipeline including continuous integration, continuous deployment, containerization, monitoring, alerting, backup automation, and infrastructure management.

---
Webhook test
## Author

**Tamilselvan Manohar**
