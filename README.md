# Assignment 3 — Kubernetes Orchestration & Full DevOps Pipeline

A 3-tier application deployed with a complete DevOps toolchain.

## Architecture
Nginx (reverse proxy, NodePort 30080) -> Flask API (REST, ClusterIP) -> MySQL (database, ClusterIP)

## Tech stack
- Docker + Docker Compose (local dev)
- GitHub Actions (CI/CD -> DockerHub)
- Kubernetes on Minikube (Deployments, Services, PV/PVC, ConfigMaps, Secrets)

## Quick start (Kubernetes)
    ./start.sh
Then open the printed URL, or:
    curl http://$(minikube ip):30080/health

## Local dev (Docker Compose)
    cd app && docker compose up -d --build
    curl http://localhost/health

## Endpoints
- GET    /health
- GET    /api/items
- POST   /api/items     {"name": "...", "description": "..."}
- DELETE /api/items/<id>
