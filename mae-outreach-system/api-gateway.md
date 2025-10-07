# API Gateway

## Overview

The API Gateway serves as the central entry point for all client applications, handling routing, authentication, and request/response processing.

## Responsibilities

### Authentication & Authorization

- JWT token verification via `svc-identity`
- Rate limiting and throttling
- CORS handling

### Routing

- Route requests to appropriate microservices
- Request/response transformation
- API versioning

## Architecture

```mermaid
%%{init: {"flowchart": {"htmlLabels": false}} }%%
flowchart TD
    %% Client Layer
    AdminWeb[Admin Web App]

    %% API Gateway
    Gateway[API Gateway]

    %% Authentication Flow
    Auth0[Auth0 Identity Provider]
    Identity[svc-identity]

    %% Backend Services
    Platform[svc-platform]
    Notifications[svc-notifications]

    %% External Services
    Email[SendGrid Email Service]

    %% Request Flow
    AdminWeb -->|1. Request with JWT| Gateway

    %% Authentication Check
    Gateway -->|2. Validate JWT| Identity
    Identity -->|3. Verify with Auth0| Auth0
    Auth0 -->|4. Token valid| Identity
    Identity -->|5. User authorized| Gateway

    %% Routing Decision
    Gateway -->|6a. Route to Platform| Platform
    Gateway -->|6b. Route to Notifications| Notifications

    %% Service Processing
    Platform -->|7. Process request| Platform
    Notifications -->|8. Send email| Email

    %% Response Flow
    Platform -->|9. Response| Gateway
    Notifications -->|10. Response| Gateway
    Gateway -->|11. Return response| AdminWeb

    %% Error Flow
    Gateway -.->|Auth failed| AdminWeb
    Gateway -.->|Service error| AdminWeb

    %% Styling
    classDef client fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef gateway fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef service fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef external fill:#fce4ec,stroke:#880e4f,stroke-width:2px
    classDef auth fill:#fff3e0,stroke:#e65100,stroke-width:2px

    class AdminWeb client
    class Gateway gateway
    class Identity,Platform,Notifications service
    class Auth0,Email external
```

## Implementation Details

- **Entry Point**: All applications use the API Gateway
- **Authentication**: JWT verification delegated to `svc-identity`
- **Routing**: Intelligent routing based on request patterns
- **Monitoring**: Request/response logging and metrics

## Security Features

- JWT token validation
- Request rate limiting
- CORS configuration

## Performance Considerations

- Response caching where appropriate
- Timeout handling

## Technology Options

- **NestJS**: Consistent with backend services
- **GCP API Gateway**: Enterprise API gateway
