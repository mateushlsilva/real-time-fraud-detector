# 🛡️ Real-Time Fraud Detector

Sistema distribuído para **detecção de fraudes em tempo real**, desenvolvido como monorepo profissional com microserviços NestJS + FastAPI (Python ML).
Arquitetura preparada para desenvolvimento local (Docker Compose) e deploy em produção na **AWS (ECS / ECR)** provisionada com **Terraform**.

---

## 🔥 Visão rápida

* Monorepo com **NestJS** para microserviços / API Gateway
* **FastAPI (Python)** para o serviço de inferência ML (`fraud-service`) e scripts de treinamento separados
* **RabbitMQ** para mensageria assíncrona
* **Redis / ElastiCache** para feature store / counters / cache
* **Postgres** para auditoria/logs
* **Docker / Docker Compose** para dev local
* **Terraform** para provisionar infra na AWS (VPC, ECS, ECR, RDS, ElastiCache, MQ)
* **GitHub Actions** para CI/CD (build images → push → terraform plan/apply)
* Monorepo orquestrado com **TurboRepo** (opcional, recomendado)

---

## 📁 Estrutura do monorepo (recomendada)

```
real-time-fraud-detector/
│
├── apps/
│   ├── api-gateway/           # NestJS
│   ├── transaction-service/   # NestJS
│   ├── auth-service/          # NestJS
│   ├── notification-service/  # NestJS
│   └── fraud-service/         # FastAPI 
│
├── packages/
│   └── commun/          # DTOs, interfaces (TS)
│
├── infra/
│   ├── terraform/           
│   └── docker/                
|
├── scripts/
│   └── training/          # Python scripts (treino com scikit-learn)
│
├── .github/workflows/
│   ├── docker-build.yaml
│   └── terraform.yaml
│
├── turbo.json
├── package.json
├── README.md
└── LICENSE
```

---

## 🛠️ Tecnologias principais

* Backend: **NestJS** (TypeScript)
* ML / Inferência: **FastAPI** (Python) — carrega modelos produzidos pelos scripts de treino
* Treinamento: **scikit-learn** 
* Mensageria: **RabbitMQ**
* Cache / feature store: **Redis**
* DB audit: **Postgres**
* Infra: **AWS (ECS / ECR / RDS / ElastiCache / AmazonMQ)** provisionado com **Terraform**
* CI/CD: **GitHub Actions**
* Container: **Docker / Docker Compose**
* Monorepo: **TurboRepo** 

---
