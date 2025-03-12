# 🛡️ Dynaroute - Dynamic API Gateway

Dynaroute is a dynamic, cloud-native API Gateway built on top of Spring Cloud Gateway. It provides real-time route management, multi-tenant support, custom routing predicates, and advanced traffic control—without requiring downtime or redeployment.

Dynaroute empowers development and operations teams to manage microservices traffic dynamically, providing an intuitive interface and APIs for adding, updating, and deleting routes on-the-fly.

---

## 🚀 Key Features

✅ **Dynamic Route Management**  
- Add, update, and delete routes at runtime  
- No need to restart or redeploy services  
- Support for in-memory, database, and distributed route storage (e.g., Redis/Postgres)

✅ **Custom Routing Predicates**  
- Route requests based on path, HTTP headers, query parameters, and JWT claims  
- Advanced predicates like Geo-location, Device Type, and Tenant ID (multi-tenant-aware routing)  
- Plug-and-play custom predicates for specific business needs  

✅ **Multi-Tenant Support**  
- Route isolation per tenant  
- Tenant-specific authentication, authorization, and rate limiting  
- Easy configuration for SaaS and B2B multi-tenant architectures  

✅ **Rate Limiting & Throttling**  
- Per-route and per-tenant rate limiting  
- Integration with Redis for distributed rate limiting  
- Support for burst control and quota management  

✅ **Load Balancing & Failover**  
- Dynamic load balancing across backend services  
- Integration with Resilience4j for circuit breaker, retry, and fallback mechanisms  

✅ **Security & Authentication**  
- Built-in JWT authentication and OAuth2 support  
- Role-based access control (RBAC) for route management APIs  
- Optional API Key or HMAC security for services  

✅ **Admin API & Dashboard (Coming Soon)**  
- RESTful Admin API for managing routes, policies, and tenants  
- Web-based Admin Dashboard (React/Angular) for easy configuration and visualization  
- Audit logs for tracking changes in routes and policies  

✅ **Observability & Monitoring**  
- Integrated request/response logging and metrics collection  
- Prometheus & Grafana integration for real-time monitoring  
- Distributed tracing (Zipkin/Jaeger) for end-to-end request flow visualization  

✅ **Pluggable Filters**  
- Built-in pre-filters and post-filters  
- Customize request/response manipulation (headers, payloads)  
- Add logging, authentication, transformation, and enrichment filters  

✅ **High Availability & Scalability**  
- Stateless gateway architecture; horizontally scalable  
- Deployable on AWS ECS, Kubernetes (EKS, AKS, GKE), or on-prem  
- Supports multi-region deployments  

---

## 🌎 Use Cases

- **SaaS Multi-Tenant Gateways**: Handle per-tenant routing and auth dynamically  
- **Microservices API Gateway**: Simplify routing, security, and traffic management for microservices  
- **B2B Integrations**: Create custom routing rules for partner organizations  
- **API Monetization**: Enforce rate limits and quotas based on subscriptions  

---

## 📦 Deployment Options

Dynaroute is designed to be flexible and cloud-native, so you can deploy it in multiple ways depending on your environment and preferences.

---

### 1️⃣ Run as a Simple JAR File (Standalone)

You can run Dynaroute as a standalone Spring Boot application directly from the JAR.

#### Prerequisites
- Java 17+  
- Maven / Gradle (optional for building)  

#### Steps
```bash
# Clone the repository
git clone https://github.com/vinod-kumar-sharma/dynaroute.git
cd dynaroute

# Build the application (optional if you use pre-built JAR)
./mvnw clean package

# Run the JAR file
java -jar target/dynaroute-gateway.jar
```

#### Access URLs
- API Gateway Base URL: `http://localhost:8080`  
- Admin API URL (Planned): `http://localhost:8080/admin`

---

### 2️⃣ Run as a Container (Docker, ECS, EKS, Azure AKS, GCP GKE)

Dynaroute comes pre-packaged as a Docker container. You can run it locally with Docker or deploy it to a container orchestration system like AWS ECS, Amazon EKS, Azure AKS, or Google GKE.

#### Docker (Local)
```bash
# Pull the Docker image (replace with your image name/tag)
docker pull your-dockerhub-user/dynaroute:latest

# Run Dynaroute in Docker
docker run -d \
  -p 8080:8080 \
  --name dynaroute-gateway \
  your-dockerhub-user/dynaroute:latest
```

#### ECS/EKS on AWS, AKS on Azure, GKE on GCP
- Ready-to-deploy Helm charts and Terraform templates are available for ECS/EKS/AKS/GKE.  
- Supports auto-scaling, multi-AZ deployments, and managed database integrations (Redis/Postgres).

> 🔹 Deploy in **ECS Fargate** for a fully serverless experience  
> 🔹 Deploy in **EKS or AKS** for Kubernetes-native scaling  
> 🔹 Integrated with AWS CloudWatch, Azure Monitor, and GCP Operations Suite for monitoring/logging

---

### 3️⃣ Available on Cloud Marketplaces (AMI / SaaS)

Dynaroute is also available on AWS Marketplace, Azure Marketplace, and Google Cloud Marketplace for instant deployment.

#### 🟢 AWS Marketplace
- Available as a pre-configured AMI (Amazon Machine Image)  
- One-click deployment on EC2 instances  
- SaaS version available on ECS/EKS with full management  
- Zero maintenance → We manage everything, including scaling, updates, and monitoring.

#### 🔵 Azure Marketplace
- Available as a Virtual Machine (VM) image  
- SaaS subscription for AKS deployments, managed by us  
- Integrated with Azure Active Directory and Azure Monitor

#### 🟣 Google Cloud Marketplace
- Available as a GCE VM Image or as a GKE container app  
- SaaS version for fully managed routing gateway  
- Integrated with Cloud Logging, Cloud Monitoring, and IAM

> 💡 Use the Marketplace version if you prefer zero management overhead and enterprise SLAs.

---

## ⚙️ Supported Platforms

✅ Local (JAR or Docker)  
✅ AWS ECS (Fargate / EC2)  
✅ AWS EKS (Kubernetes)  
✅ Azure AKS  
✅ Google GKE  
✅ Cloud VM/AMI images (EC2, Azure VMs, GCE)  
✅ SaaS deployments with fully managed hosting  

---

## 🌎 Benefits of Marketplace Deployment

✔️ One-click installation on your cloud platform  
✔️ No need to manage servers, containers, or updates  
✔️ Managed scaling, backups, and monitoring  
✔️ Enterprise support and SLAs  
✔️ Pay-as-you-go or subscription-based billing via your cloud provider  

---

## 📦 Getting Started

### Prerequisites
- Java 17+  
- Maven / Gradle  
- Redis (Optional for rate limiting and route storage)  
- Postgres / MySQL (Optional for persistent route management)  
- Docker (Optional for containerized deployment)

### Clone the Repository
```bash
git clone https://github.com/your-org/dynaroute.git
cd dynaroute
```

### Build & Run
```bash
# Build the application
./mvnw clean install

# Run the gateway
java -jar target/dynaroute-gateway.jar
```

### Access the Gateway
- API Gateway Base URL: `http://localhost:8080`  
- Admin API URL (planned): `http://localhost:8080/admin`

---

## 📝 Roadmap

Here’s what’s planned for the next releases:  
- [x] Dynamic route management via REST API  
- [x] Custom predicates and filters  
- [ ] Multi-tenant routing and isolation  
- [ ] Admin Dashboard (React/Angular)  
- [ ] Distributed configuration (Redis/DB)  
- [ ] JWT/OAuth2 integration  
- [ ] Rate limiting and quota management  
- [ ] Prometheus/Grafana observability  
- [ ] OpenTelemetry tracing integration  
- [ ] Canary deployments & A/B testing  
- [ ] AWS Marketplace Listing (AMI/SaaS)

✨ Want to suggest a feature? Open an issue on GitHub or contact us!

---

## 🏗️ Architecture (High Level)

```
 ┌────────────────────┐
 │     Clients        │
 └────────────────────┘
           │
           ▼
 ┌────────────────────────────┐
 │      Dynaroute Gateway     │
 │  ────────────────────────  │
 │  ▪ Dynamic Routing Engine  │
 │  ▪ Predicate Filters       │
 │  ▪ Rate Limiter            │
 │  ▪ Load Balancer           │
 └────────────────────────────┘
           │
           ▼
 ┌────────────────────────────┐
 │ Backend Microservices      │
 └────────────────────────────┘
```

---

## 🛠️ Tech Stack

- Backend Framework: Spring Boot, Spring Cloud Gateway  
- Reactive Programming: Project Reactor  
- Security: Spring Security, OAuth2, JWT  
- Persistence: Redis, PostgreSQL/MySQL (optional)  
- Admin Dashboard (Planned): React/Angular  
- Monitoring: Micrometer, Prometheus, Grafana  
- CI/CD: Jenkins, Spinnaker, GitHub Actions (optional)  
- Containerization: Docker, Kubernetes (EKS compatible)  

---

## 📜 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Contributing

We welcome contributions! Please read our CONTRIBUTING.md for details on how to get started.

---

## ⭐ Stay Connected

If you like this project, consider giving it a ⭐ and sharing it with others!
