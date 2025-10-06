# Monorepo Structure

## Overview

The insurance outreach platform uses Nx to manage multiple applications, services, and shared libraries in a single repository. This enables consistent tooling, fast builds via caching, strong module boundaries, and scalable team workflows.

## Workspace Structure (recommended)

```
insurance-outreach/
├── apps/                              # UI and edge apps
│   ├── admin-web/                     # Admin React app
│   └── api-gateway/                   # API Gateway (Nest)
├── services/                          # Backend microservices (Nest)
│   ├── svc-identity/                  # Authentication & authorization
│   ├── svc-platform/                  # Members, specialists, calls, risk
│   └── svc-notifications/             # Email notifications
├── libs/                              # Shared libraries
│   ├── shared/                        # Shared utilities and types
│   ├── ui/                            # Shared UI components
│   ├── data-access/                   # Data access layers
│   └── feature/                       # Feature-specific libraries
├── tools/                             # Repo-wide scripts & generators
├── infra/                             # IaC and ops artifacts
├── .github/workflows/                 # CI on GitHub Actions
```
