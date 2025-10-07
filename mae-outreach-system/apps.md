# Applications

## Overview

The platform ships two applications: a web-based Admin portal for internal operations and an API Gateway that fronts all backend services.

## Current Applications

### Admin Web

- **Technology**: React with Vite
- **Purpose**: Administrative interface for platform management
- **Users**: Outreach Specialists
- **Features**: User management, system configuration, analytics, outreach workflows (CSV import, queues, risk review)

### API Gateway

- **Technology**: NestJS (Node.js)
- **Purpose**: Single entry point for clients; request routing, auth, rate limiting, response aggregation
- **Users**: Admin Web, automated integrations
- **Features**: Authentication (JWT), RBAC enforcement, observability

## Development Approach

- Shared component library for consistent UI/UX
- Independent deployment pipelines (gateway and admin web deploy separately)
- Monorepo-managed with Nx (affected-based builds, caching)
- Feature flags for iterative rollout of Admin Web features (launchdarkly)

## Technology Stack

### Admin Web

- **Frontend Framework**: React 18+
- **Build Tool**: Vite
- **State Management**: Redux Toolkit
- **Styling**: Tailwind CSS
- **Testing**: Vitest or Jest

### API Gateway

- **Framework**: NestJS (Express adapter)
- **Validation**: class-validator / Zod
- **Auth**: JWT (user), API tokens (M2M)
- **Observability**: Winston, Papertrail
- **Testing**: Vitest or Jest
