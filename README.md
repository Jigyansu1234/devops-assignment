🚀 DevOps Assignment

This project demonstrates a microservices setup with:

- Two backend services: a **Golang** service and a **Python Flask** service.
- An **NGINX reverse proxy** that routes traffic to these services via distinct paths.
- All services are containerized using **Docker** and orchestrated with **Docker Compose**.

---

## 📦 Project Structure

devops-assignment/
├── nginx
│   ├── Dockerfile
│   └── nginx.conf
├── service_1
│   ├── Dockerfile
│   └── main.go
├── service_2
│   ├── Dockerfile
│   ├── app.py
│   ├── pyproject.toml
│   └── uv.lock
└── README.md
├── docker-compose.yml



⚙️ Setup Instructions

 **Note:** 
✅ Note: This project is deployed on an AWS EC2 instance. Replace localhost with the EC2 Public IP for testing. 
If the instance is not running, services may not respond — this is done to manage cloud usage costs efficiently.


 ##### Prerequisites #####

- Docker & Docker Compose installed
- Ports `80`, `8001`, and `8002` open in the EC2 security group

##### Run the Application  #######

docker-compose up --build -d

Stop the Application = docker-compose down


Routing via NGINX (Reverse Proxy)
The NGINX container exposes port 80 and routes incoming requests to the appropriate backend:

Route	      Target Service	        Port Mapped
/service1	  Golang Service	        8001
/service2 	Python Flask Service	  8002

Example URLs:
http://54.144.246.133/8001/hello
http://54.144.246.133/8002/ping

YOUR_EC2_PUBLIC_IP with your real IP (e.g., http://54.144.246.133):

http://YOUR_EC2_PUBLIC_IP/service1/hello
http://YOUR_EC2_PUBLIC_IP/service2/ping



Health Checks (Bonus ✅)
Both services expose a /ping endpoint for health monitoring. These are configured using Docker health checks:

Golang service → /ping

Flask service → /ping

Docker Compose waits until both services are healthy before starting NGINX.


Bonus Points Implemented
Feature	Implemented
Health checks	
Modular Docker setup
NGINX reverse proxy	
Logging Clarity	
Single port accessibility



🛠️ Technologies Used
Docker

Docker Compose

NGINX

Golang

Python (Flask)

AWS EC2 (Ubuntu 22.04)


🙏 Final Note
If the application does not respond during testing, the EC2 server may be temporarily
stopped to manage usage costs. Please contact me if you would like the server to be restarted for review.











