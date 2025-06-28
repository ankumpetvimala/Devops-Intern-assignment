# 🔁 Nginx Reverse Proxy with Docker Compose

This project sets up a reverse proxy using **Nginx** and **Docker Compose** to route traffic to two microservices:

- A Python application
- A Golang application

The Nginx container handles incoming HTTP requests and routes them based on the path prefix (`/service1`, `/service2`).

---

## 📁 Project Structure

project-root/

│ 

   ├── docker-compose.yml 

   ├── nginx/ 

        ├── nginx.conf

         └── Dockerfile 

   ├── service_1/ ← Golang app │ 

         └── Dockerfile 
   
   ├── service_2/ ← Python app │ 

         └── Dockerfile 
   
└── README.md


---

### Services and Ports

| Service   | Description                                 | Port |
|-----------|---------------------------------------------|------|
| service1  | Go backend, responds with service info      | 8001 |
| service2  | Python Flask backend, responds with info    | 8002 |
| nginx     | Reverse proxy, handles all routing          | 8080 |


## Setup & Execution

### Prerequisites

  Installations:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)

### Steps to Run

1. Clone this repository:
   
      git clone https://github.com/your-username/your-repo-name.git
   
      cd your-repo-name
   
2. Build and start all services:

      docker-compose up --build

3. Access services via your browser:

      `http://localhost:8080/service1/ping` { "service": "service1" }
   
      `http://localhost:8080/service2/hello`	{ "service": "service2" }

   Replace localhost with your EC2 IP if running on AWS, e.g., http://3.82.203.38:8080/service1
   

### ⚙️ How It Works

- Nginx listens on port 8080 and routes:

  Nginx routes incoming requests based on the URL path

 /service1/ → forwards to service1:8001 ( Golang service)

 /service2/ → forwards to service2:8002 (Python service)

 This is configured in nginx/default.conf.

  
### 🩺 Health Checks

Each service exposes a basic HTTP endpoint:

GET /ping for service1

GET /hello for service2

These return static JSON indicating the service is running.

### 🔍 Logs

Check access logs for requests routed through Nginx:

docker-compose logs nginx

## Conclusion 

This project uses Docker to run two services: one in Go and one in Python. NGINX works as a reverse proxy to manage and route requests to each service.









