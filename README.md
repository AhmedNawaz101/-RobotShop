# Stan's Robot Shop

A cloud-native microservices e-commerce platform demonstrating distributed architecture patterns across multiple cloud providers. Built with polyglot services (Node.js, Python, Java, PHP, Go), it supports deployment on Kubernetes variants (AKS, EKS, GKE), Docker Swarm, and DCOS. Features integrated logging via Fluentd, comprehensive monitoring, and load testing capabilities.

## Overview

Stan's Robot Shop is a sample microservice application designed as a sandbox to test and learn containerized application orchestration and monitoring techniques. It showcases real-world patterns for building, deploying, and managing microservices across different orchestration platforms.

## Architecture

The application follows a microservices architecture with the following services:

| Service | Language | Purpose |
|---------|----------|---------|
| **web** | Nginx/AngularJS | Frontend web interface |
| **cart** | Node.js (Express) | Shopping cart management |
| **catalogue** | Node.js (Express) | Product catalog |
| **user** | Node.js (Express) | User authentication & management |
| **payment** | Python (Flask) | Payment processing |
| **shipping** | Java (Spring Boot) | Shipping calculations |
| **ratings** | PHP (Apache) | Product ratings & reviews |
| **dispatch** | Go | Order dispatch service |

### Data & Infrastructure Services

| Service | Technology | Purpose |
|---------|-----------|---------|
| **MongoDB** | NoSQL Database | Document storage for catalogue, users |
| **MySQL** | Relational Database | Ratings & transactional data |
| **Redis** | In-Memory Cache | Session management, caching |
| **RabbitMQ** | Message Queue | Asynchronous messaging |
| **Fluentd** | Log Aggregator | Centralized logging |

## Technologies Stack

### Languages & Frameworks
- **Node.js** with Express.js
- **Python** with Flask
- **Java** with Spring Boot
- **Go**
- **PHP** with Apache
- **AngularJS** (Frontend)

### Container & Orchestration
- **Docker** - Containerization
- **Docker Compose** - Local development
- **Kubernetes** - Production orchestration
- **Helm** - Kubernetes package management

### Cloud Platforms
- **AWS EKS** - Elastic Kubernetes Service
- **Azure AKS** - Azure Kubernetes Service
- **Google GKE** - Google Kubernetes Engine
- **Docker Swarm** - Container orchestration
- **DCOS** - Datacenter Operating System

### Databases & Messaging
- **MongoDB** - NoSQL database
- **MySQL** - Relational database
- **Redis** - In-memory data store
- **RabbitMQ** - Message broker

### Monitoring & Logging
- **Fluentd** - Log aggregation
- **Instana** - Application performance monitoring
- **Prometheus** - Metrics collection

## Project Structure

```
E-Commerce-Store/
├── web/                 # Frontend application
├── cart/               # Cart microservice
├── catalogue/          # Catalogue microservice
├── user/               # User microservice
├── payment/            # Payment microservice
├── shipping/           # Shipping microservice
├── ratings/            # Ratings microservice
├── dispatch/           # Dispatch microservice
├── mongo/              # MongoDB configuration
├── mysql/              # MySQL configuration
├── redis/              # Redis cache
├── fluentd/            # Log aggregation
├── load-gen/           # Load generation tools
├── K8s/                # Kubernetes deployments
├── AKS/                # Azure Kubernetes Service
├── EKS/                # AWS Elastic Kubernetes Service
├── GKE/                # Google Kubernetes Engine
├── Swarm/              # Docker Swarm
├── DCOS/               # DataCenter OS
├── OpenShift/          # OpenShift deployments
└── docker-compose.yaml # Local development setup
```

## Getting Started

### Quick Start with Docker Compose

```bash
# Clone the repository
git clone <repository-url>
cd E-Commerce-Store--main

# Start all services
docker-compose up -d

# Access the application
# Web UI: http://localhost:8080
```

### Local Development

```bash
# Build images from source
docker-compose build

# Run services
docker-compose up
```

## Deployment Guides

### Kubernetes Deployment
See [K8s/README.md](K8s/README.md) for Kubernetes deployment instructions.

### Cloud-Specific Deployments

- **AWS EKS**: [EKS Deployment Guide](EKS/01-prerequisites.md)
- **Azure AKS**: [AKS Deployment Guide](AKS/README.md)
- **Google GKE**: [GKE Deployment Guide](GKE/README.md)
- **Docker Swarm**: [Swarm Deployment Guide](Swarm/deploy.sh)
- **DCOS**: [DCOS Deployment Guide](DCOS/deploy.sh)
- **OpenShift**: [OpenShift Deployment Guide](OpenShift/setup.sh)

## Load Testing

Generate realistic load against the application:

```bash
cd load-gen
docker build -t load-gen:latest .
docker run -e "ROBOTSHOP_URL=http://<app-url>" load-gen:latest
```

See [load-gen/README.md](load-gen/README.md) for detailed instructions.

## Monitoring & Logging

### Fluentd Setup
Centralized log aggregation is configured via Fluentd.

- Docker Compose: [Docker-Compose/README.md](fluentd/Docker-Compose/README.md)
- Kubernetes: [Kubernetes/README.md](fluentd/Kubernetes/README.md)

### Instana Integration
Services include Instana agent integration for comprehensive monitoring and tracing. An Instana account is required to view results.

[Get a free Instana trial](https://instana.com/trial)

## API Services

Each microservice exposes REST APIs:

- **Cart API**: `http://localhost:8001/api/cart`
- **Catalogue API**: `http://localhost:8002/api/catalogue`
- **User API**: `http://localhost:8003/api/user`
- **Payment API**: `http://localhost:8004/api/payment`
- **Shipping API**: `http://localhost:8005/api/shipping`
- **Ratings API**: `http://localhost:8006/api/ratings`

## Key Features

✅ **Polyglot Microservices** - Multiple languages and frameworks  
✅ **Multi-Cloud Ready** - Deploy to any major cloud provider  
✅ **Multiple Orchestration Platforms** - Kubernetes, Swarm, DCOS, OpenShift  
✅ **Comprehensive Monitoring** - Instana integration for APM  
✅ **Centralized Logging** - Fluentd log aggregation  
✅ **Load Testing Tools** - Built-in load generation  
✅ **Production Patterns** - Cache, messaging, database patterns  
✅ **Infrastructure as Code** - Helm charts, deployment manifests  

## Use Cases

- Learning microservices architecture
- Testing container orchestration platforms
- Evaluating monitoring and logging solutions
- Load testing applications
- Demonstrating cloud-native deployment patterns
- Training on DevOps and containerization

## Important Notes

⚠️ This is a demonstration application intended for learning purposes.

- Error handling is intentionally minimal
- No security features are implemented
- Not suitable for production use as-is
- Designed for educational and testing scenarios

## Contributing

Contributions are welcome! This project is designed as a learning resource.

## License

Apache License 2.0

## Resources

- [Original Blog Post](https://www.instana.com/blog/stans-robot-shop-sample-microservice-application/)
- [Instana Monitoring Documentation](https://docs.instana.io/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Docker Documentation](https://docs.docker.com/)

## Support & Community

For issues, questions, or contributions:
- Check existing documentation in the project folders
- Review deployment guides for your target platform
- Consult the Instana documentation for monitoring issues

---

**Built to learn. Designed to teach. Ready to scale.**
