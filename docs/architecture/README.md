# Architecture 🏗️

## System Overview

Nexa Pay is built on a microservices architecture:

```
┌─────────────────────────────────────────┐
│         Client Applications             │
│  (Web, Mobile, Desktop)                │
└────────────┬────────────────────────────┘
             │
┌────────────▼────────────────────────────┐
│      API Gateway / Load Balancer        │
└────────────┬────────────────────────────┘
             │
┌────────────▼──────────────┬────────────┐
│  Nexa Core (Payment API)  │  Auth SVC  │
├──────────────────────────┤────────────┤
│  Card Management         │ JWT/OAuth2 │
│  Transaction Processing  │ 2FA/MFA    │
│  User Management         │ Session    │
└────────────┬──────────────┴────────────┘
             │
┌────────────▼────────────────────────────┐
│    Data & Services Layer                │
├─────────────────┬──────────────────────┤
│  PostgreSQL DB  │  Redis Cache         │
│  Storage (S3)   │  Message Queue (RMQ) │
└────────────────┴──────────────────────┘
```

## Components

### Frontend
- Web Application (Next.js)
- Mobile App (React Native)
- Admin Dashboard

### Backend
- **nexa-core** - Main payment and transaction API
- **nexa-auth** - Authentication and authorization
- **nexa-reports** - Analytics and reporting

### Infrastructure
- Kubernetes orchestration
- PostgreSQL primary database
- Redis cache layer
- RabbitMQ message queue

## Technology Stack

- **Language**: TypeScript, Node.js
- **Framework**: Express, Next.js, React Native
- **Database**: PostgreSQL, Redis
- **Deployment**: Kubernetes, Docker
- **CI/CD**: GitHub Actions

---

See [Infrastructure](./infrastructure.md) for deployment details.