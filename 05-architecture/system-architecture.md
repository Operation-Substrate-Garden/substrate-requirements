# System Architecture

The Operation Substrate Garden architecture is designed to be scalable, secure, and distributed across multiple interaction points (Web and App), all anchored by a robust backend.

## 1. System Overview

This diagram shows the primary components of the system and their high-level interaction.

```mermaid
graph TD
    User([User])
    
    subgraph Frontend_Substrate [Client Layer]
        WebApp[substrate-web]
        MobileApp[substrate-app]
    end
    
    subgraph Backend_Substrate [Core Layer]
        API[substrate-backend]
        DB[(PostgreSQL / Vector DB)]
    end
    
    User -->|Accesses via Web| WebApp
    User -->|Accesses via Mobile| MobileApp
    
    WebApp -->|REST / GraphQL| API
    MobileApp -->|REST / GraphQL| API
    
    API <-->|Stores & Fetches Data| DB
    
    WhitelistService[Organization Whitelist Service]
    API -->|Verifies Membership| WhitelistService
```

## 2. Component Responsibilities

### substrate-backend
The central logic of the system. It is responsible for:
- **User Management**: Authentication, profiles, and organization verification.
- **Community Entities**: Managing community lifecycle (creation, updates, visibility).
- **Topic Entities**: Handling the hierarchy of topics within communities.
- **Security & Permissions**: Ensuring that users only see what they are authorized to see based on their "Tactical Meta-data."

### substrate-web
The primary desktop and browser-based interface.
- Follows the "Tactical Elegance" design system.
- Focuses on "Community Hub" and "Substrate Map" visualization for larger screens.

### substrate-app
The native mobile application for on-the-go access.
- Optimized for "Mobile Tactical Input Fields."
- Provides real-time notifications for topic updates within joined communities.

## 3. Core Domain Model

```mermaid
erDiagram
    ORGANIZATION ||--o{ USER : "whitelists"
    USER ||--o{ COMMUNITY_MEMBERSHIP : "joins"
    COMMUNITY ||--o{ COMMUNITY_MEMBERSHIP : "has members"
    COMMUNITY ||--o{ TOPIC : "hosts"
    USER ||--o{ TOPIC_DISCUSSION : "participates in"
    TOPIC ||--o{ TOPIC_DISCUSSION : "contains"
```