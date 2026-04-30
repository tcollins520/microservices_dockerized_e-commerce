📌 Project Overview

This project demonstrates a containerized microservices-based e-commerce application using Docker. The application is composed of multiple independent services that communicate with each other to deliver a complete shopping experience.

The goal of this project is to showcase modern DevOps practices including containerization, service isolation, and scalable architecture design.
________________________________________
🏗️ Architecture Overview
Client → Frontend → API Gateway → Microservices → Database
________________________________________
# Prerequisites
- node 14
- JRE 8
- Maven 3.9
- MySQL 8
- MongoDB
________________________________________

🧰 Tech Stack
Docker (Containerization)
Docker Compose (Service orchestration)
Java / Spring Boot (Backend services)
Node.js / Frontend (UI)
REST APIs (Service communication)
AWS (ECR, ECS/EKS integration - optional)
Each service runs in its own container, allowing independent scaling and deployment.
________________________________________
📦 Microservices Included
🛍️ Product Service – Manages product catalog
🛒 Cart Service – Handles shopping cart logic
📦 Order Service – Processes customer orders
👤 User Service – Authentication & user management
🌐 Frontend Service – User interface
⚙️ How It Works
Each microservice is containerized using Docker
Docker Compose orchestrates all services
Services communicate via REST APIs
Frontend interacts with backend services through APIs
________________________________________
🚀 Getting Started
🔧 Prerequisites
Docker installed
Docker Compose installed
▶️ Run the application
docker-compose up --build
🌐 Access the app
http://localhost:<PORT>
🐳 Docker Highlights
Multi-container architecture
Service isolation
Reproducible environments
Easy local development setup
🔄 CI/CD Integration (Optional Extension)
________________________________________
This project can be integrated with a CI/CD pipeline:

Build Docker images via Jenkins
Push images to Amazon ECR
Deploy to ECS or Kubernetes (EKS)
🧠 Key Concepts Demonstrated
Microservices architecture
Containerization with Docker
Service-to-service communication
Scalable application design
DevOps-ready deployment strategy
________________________________________

Microservices improve scalability and flexibility by allowing independent deployment and scaling of services. ()

🚀 Future Improvements
Kubernetes (EKS) deployment
Helm chart implementation
Centralized logging (ELK stack)
Monitoring (Prometheus + Grafana)
API Gateway integration
CI/CD pipeline automation

👩🏽‍💻 Author

Tina Collins
DevOps Engineer | Cloud Enthusiast | Lifelong Learner
