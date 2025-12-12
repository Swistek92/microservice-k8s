# Marketzooo — Cloud‑Native Microservices Platform

**NestJS • Kubernetes • K3s • GKE • ArgoCD • Prometheus • Grafana • RabbitMQ • gRPC • GitOps**

Marketzooo is a lightweight cloud‑native microservices platform showcasing real production practices using Kubernetes, GitOps automation, observability, scalable communication patterns, and CI/CD.

---

## 🚀 What the Platform Includes

- Multiple NestJS microservices (Auth, Users, Products, Orders)
- API Gateway as the single public entry point
- gRPC, TCP, and RabbitMQ communication
- Kubernetes deployments (GKE + K3s)
- Automated GitOps CD using **Argo CD**
- Monitoring with **Prometheus + Grafana**
- Automatic HTTPS with **cert‑manager + Traefik**
- CI pipelines powered by GitHub Actions

---

## 📦 Architecture (Short Overview)

All client traffic flows through the **API Gateway**, which routes requests to microservices using various protocols:

```
Client → Load Balancer → Ingress → API Gateway
                │
                ├─ Auth‑MS (TCP)
                ├─ Users‑MS (TCP + TLS)
                ├─ Products‑MS (gRPC)
                └─ Orders‑MS (RabbitMQ Events)
```

---

## 🖥 Kubernetes Cluster View (k9s)

A high‑level view of all microservices, system components, and monitoring stack:

![k9s cluster overview](https://iili.io/fqFJVXs.png)

---

## 🔄 Argo CD – GitOps Deployment

### Applications Overview

Argo CD keeps your cluster fully synchronized with the Git repository.

![Argo CD Applications](https://iili.io/fqFkT91.png)

### Microservices Deployment Tree

A complete visual overview of all deployed resources:

![Argo CD Application Tree](https://iili.io/fqFvt14.png)

---

## 📊 Monitoring (Grafana + Prometheus)

Dashboards provide:

- API Gateway resource usage
- Orders per minute statistics
- Cluster performance metrics
- Microservice‑level CPU/MEM

![Grafana Dashboard](https://iili.io/fqF5Liv.png)

---

## 🔐 TLS & Security (Short)

- HTTPS provided by **cert‑manager + Let’s Encrypt**
- Traefik handles routing
- Automatic certificate renewal
- All public endpoints fully encrypted

---

## 🔁 CI/CD (GitOps + CI)

1. Push to GitHub
2. CI builds Docker images
3. Images uploaded to Google Artifact Registry
4. Argo CD performs automatic rollout

---

## 🧭 Roadmap (Future Enhancements)

- **OpenTelemetry tracing** (collector + Jaeger/Tempo)
- **Service Mesh** (mTLS, retries, traffic shaping)
- Advanced dashboards and business metrics
- Slack/Telegram alerting
- Rate limits + error tracking at API Gateway

---

## 📁 Repository Layout

```
k8s/
 ├── app-k3s/
 ├── gke/
 ├── monitoring/
 └── argocd-apps/
```

---

## ✅ Summary

Marketzooo is a complete cloud‑native microservices environment built with modern DevOps practices.  
It demonstrates GitOps, CI/CD, TLS automation, monitoring, and Kubernetes orchestration — perfect for learning, showcasing, and real‑world portfolio use.
