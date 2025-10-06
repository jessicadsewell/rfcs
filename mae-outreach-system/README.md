# Insurance Outreach Platform RFC

## Overview

This RFC outlines the architecture and implementation plan for an insurance outreach platform. The system is designed as a microservices-based architecture with a single frontend Admin application, API gateway, and backend services.

## Architecture Summary

The platform consists of:

- **Frontend Applications**: Admin web interface
- **API Gateway**: Centralized entry point with JWT authentication
- **Microservices**: Identity service and platform service for core business logic
- **Datastores**: PostgreSQL databases with TypeORM and soft deletes
- **Job Queues**: Background processing with Bull/BullMQ and Redis
- **Risk Management**: Comprehensive risk flagging and tracking system
- **DevOps**: Monitoring, logging, and CI/CD pipeline

## Table of Contents

- [Applications](./apps.md) - Frontend applications and user interfaces
- [API Gateway](./api-gateway.md) - Centralized API routing and authentication
- [Services](./services.md) - Backend microservices architecture
- [Datastores](./datastores.md) - Database design and data persistence
- [Job Queues](./job-queues.md) - Background job processing with NestJS queues
- [Monorepo](./monorepo.md) - Nx monorepo structure and organization
- [Security & Compliance](./security-compliance.md) - HIPAA compliance and security requirements
- [DevOps](./devops.md) - Monitoring, logging, and observability
- [Infrastructure](./infrastructure.md) - Deployment, scaling, and CI/CD

## Key Technologies

- **Frontend**: React, Vite
- **Backend**: NestJS
- **Database**: PostgreSQL, TypeORM
- **Authentication**: JWT, Auth0 (external identity provider)
- **Queues**: Bull/BullMQ with Redis, BullBoard monitoring
- **Monorepo**: Nx for workspace management
- **Security**: HIPAA-compliant encryption, audit logging, soft deletes
- **Monitoring**: Sentry, BullBoard
- **Logging**: Winston, Papertrail
- **Cloud**: GCP (proposed)
- **CI/CD**: GitHub Actions

## Key Features

- **Member Management**: Comprehensive member profiles with encrypted PHI
- **Call Tracking**: Complete call records with scheduling and outcomes
- **Risk Flagging**: Specialist-driven risk identification and management
- **Insurance Plans**: Multi-plan support with specialist expertise matching
- **Specialist Management**: Expertise tracking and certification management
- **Audit Trail**: Complete HIPAA-compliant audit logging
- **Background Processing**: Asynchronous job processing for scalability
- **Soft Deletes**: Data integrity with recoverable deletions
