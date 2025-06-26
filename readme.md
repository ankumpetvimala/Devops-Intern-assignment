# DevOps Assignment – Nginx Reverse Proxy + Docker

This project sets up a simple microservices system using **Docker Compose**. It includes:

- Two backend services (one in Go, one in Python)
- An **Nginx reverse proxy** container that routes traffic to these services based on the URL path
- Health checks and logging support (bonus)

---

## ✅ Services Overview

| Service     | Description                             | Port  |
|-------------|-----------------------------------------|-------|
| service1    | Go backend, responds with service info  | 8001  |
| service2    | Python Flask backend, responds with info| 8002  |
| nginx       | Reverse proxy, handles all routing      | 8080  |

---

## ⚙️ Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/satyapadamati/devops-assignment-q2-2025.git
cd devops-assignment-q2-2025

2. Run with Docker Compose

docker-compose up --build

3. Access the services via Nginx
URL	Response
http://localhost:8080/service1/ping	{ "service": "service1" }
http://localhost:8080/service2/hello	{ "service": "service2" }

Replace localhost with your EC2 IP if running on AWS, e.g., http://13.220.209.50:8080/...

🌐 How Routing Works
Nginx routes incoming requests based on the URL path:

/service1/ → forwards to service1:8001

/service2/ → forwards to service2:8002

This is configured in nginx/default.conf.

🩺 Health Check (Bonus)
Each service exposes a basic HTTP endpoint:

GET /ping for service1

GET /hello for service2

These return static JSON indicating the service is running.

📁 Project Structure

├── docker-compose.yml
├── nginx
│   ├── default.conf
│   └── Dockerfile
├── service_1
│   ├── main.go
│   └── Dockerfile
├── service_2
│   ├── app.py
│   └── Dockerfile
└── README.md

👨‍💻 Author
Satyakiran Padamati
Email: satyapadamati5@gmail.com
GitHub: https://github.com/satyapadamati


Execution screens
![Screenshot (4)](https://github.com/user-attachments/assets/9de102f9-2515-46cf-b4b4-a9fb0302640d)
![Screenshot (3)](https://github.com/user-attachments/assets/9acc910e-b01c-44b5-b04c-adf9be8d3fec)
![Screenshot (2)](https://github.com/user-attachments/assets/a647f69e-bbc8-4ee3-88d0-9dd39802e076)
hots:










