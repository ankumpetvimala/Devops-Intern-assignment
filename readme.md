📘 DevOps Assignment – Q2 2025
This is a simple DevOps project with two backend services and an Nginx reverse proxy, all running in Docker containers using Docker Compose.

🛠 Setup Instructions
bash
Copy
Edit
# Clone the repo
git clone https://github.com/<your-username>/devops-assignment-q2-2025.git
cd devops-assignment-q2-2025

# Build and run everything
docker-compose up --build
Once running, access the services via:

http://localhost:8080/service1 → returns Go service JSON

http://localhost:8080/service2 → returns Python Flask service JSON

🔀 Routing Logic
Nginx reverse proxy routes incoming traffic:

Path	Backend Service	Route Mapped To
/service1	Go backend (service1)	/ping
/service2	Python Flask (service2)	/hello

This is done using nginx/default.conf with proxy_pass.

✅ Bonus Implemented
✅ Clean Docker setup for Go and Python

✅ Reverse proxy with Nginx

✅ Docker Compose orchestration

✅ Basic Nginx logging enabled

✅ Health checks (add this if you’ve included it)

🖼 Project Structure
go
Copy
Edit
.
├── docker-compose.yml
├── nginx
│   ├── default.conf
│   └── Dockerfile
├── service_1
│   ├── Dockerfile
│   └── main.go
├── service_2
│   ├── Dockerfile
│   └── app.py
└── README.md
✅ STEP 4: Final Check & Submit
✅ Open the repo in browser

✅ Confirm all files are visible

✅ Share the link with the reviewer (e.g., paste it in the submission form)

Example:

bash
Copy
Edit
GitHub Repository: https://github.com/<your-username>/devops-assignment-q2-2025
If you’d like, I can:

Review your final GitHub repo before you submit

Help you polish README further

Help you add logs or health checks for bonus

Just drop your GitHub link and I’ll take a look! 🚀
