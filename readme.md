# 🛡️ Auto-Healing Microservices System

_A self-healing microservice architecture with Docker, Flask, Prometheus, and Grafana_

---

## 📦 System Architecture
![System Architecture](architecture-diagram.png)

---

## 🚀 Quick Start (Clone & Build)
```bash
git clone https://github.com/Dasmat13/autohealing-microservices.git
cd autohealing-microservices
docker-compose up -d --build
🐳 Quick Start (Docker Hub Pull & Run)
If you don’t want to clone the repo, you can pull images directly from Docker Hub.

bash
Copy
Edit
# Pull images
docker pull dasmat/autohealing-service-a:latest
docker pull dasmat/autohealing-service-b:latest
docker pull dasmat/autohealing-prometheus:latest
docker pull dasmat/autohealing-grafana:latest
docker pull nginx:latest
docker pull containrrr/watchtower:latest

# Run via docker-compose (using provided docker-compose.yml)
docker-compose up -d
🌐 Access Endpoints
Component	URL	Credentials
Service A	http://localhost/a	-
Service B	http://localhost/b	-
Prometheus	http://localhost:9090	-
Grafana	http://localhost:3000	admin:admin

🔧 Key Features
Self-healing: Watchtower auto-restarts failed containers

Monitoring: Prometheus scrapes metrics every 15s

Visualization: Pre-configured Grafana dashboards

Load Balancing: Nginx distributes traffic

🛠️ Troubleshooting


Common fixes:

bash
Copy
Edit
# Rebuild single service
docker-compose up -d --build service-a

# Check container health
docker ps --filter "health=unhealthy"
📚 Documentation
Prometheus Configuration

Flask Service Setup

📜 License
MIT © 2025 Dasmat