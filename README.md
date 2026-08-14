# Enterprise Management Platform

> A production-oriented Enterprise Management Platform built with **ASP.NET Core, .NET, EF Core, SQL Server, Redis, Angular, TypeScript, Docker, and GitHub Actions**, designed to demonstrate modern enterprise software architecture, security, scalability, maintainability, and DevOps practices.

![.NET](https://img.shields.io/badge/.NET-10-512BD4?logo=dotnet\&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-Web%20API-512BD4?logo=dotnet\&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-21-DD0031?logo=angular\&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript\&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-Database-CC2927?logo=microsoftsqlserver\&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?logo=redis\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?logo=docker\&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?logo=githubactions\&logoColor=white)

---

## Table of Contents

* [Overview](#overview)
* [Project Goals](#project-goals)
* [Key Features](#key-features)
* [Domain](#domain)
* [Technology Stack](#technology-stack)
* [Architecture](#architecture)
* [Backend Architecture](#backend-architecture)
* [Frontend Architecture](#frontend-architecture)
* [Project Structure](#project-structure)
* [Domain Model](#domain-model)
* [Authentication & Authorization](#authentication--authorization)
* [Dynamic Permission System](#dynamic-permission-system)
* [Organization Management](#organization-management)
* [Workflow](#workflow)
* [Audit Logging](#audit-logging)
* [Notifications](#notifications)
* [File Management](#file-management)
* [Caching](#caching)
* [API Design](#api-design)
* [Validation & Error Handling](#validation--error-handling)
* [Database](#database)
* [Performance](#performance)
* [Testing Strategy](#testing-strategy)
* [Docker](#docker)
* [Docker Compose](#docker-compose)
* [CI/CD](#cicd)
* [Security](#security)
* [Observability](#observability)
* [Architecture Decision Records](#architecture-decision-records)
* [Documentation](#documentation)
* [Screenshots](#screenshots)
* [Getting Started](#getting-started)
* [Development Workflow](#development-workflow)
* [Environment Configuration](#environment-configuration)
* [API Documentation](#api-documentation)
* [Roadmap](#roadmap)
* [Engineering Principles](#engineering-principles)
* [Portfolio Value](#portfolio-value)
* [License](#license)

---

# Overview

**Enterprise Management Platform** is a full-stack enterprise application designed to manage organizational structures, employees, users, roles, permissions, workflows, notifications, files, and audit records.

The project is intentionally designed around real-world enterprise requirements rather than a simple CRUD application.

The primary objective is to demonstrate practical experience with:

* Enterprise application architecture
* Clean Architecture
* Domain-Driven Design principles
* CQRS
* SOLID principles
* RESTful API design
* Authentication and authorization
* Dynamic permission management
* Entity Framework Core
* SQL Server
* Redis caching
* Angular
* Reactive Forms
* RxJS
* Signals
* Automated testing
* Docker
* CI/CD
* Security
* Logging and auditing
* Performance optimization

---

# Project Goals

The project has four primary goals.

### 1. Enterprise Architecture

Demonstrate how a large application can be structured into independent layers with clear responsibilities.

### 2. Production-Oriented Engineering

Implement features and infrastructure commonly required in enterprise applications:

* Authentication
* Authorization
* Auditing
* Caching
* Validation
* Error handling
* Pagination
* Filtering
* Sorting
* File management
* Notifications
* Background processing
* Testing
* CI/CD

### 3. Maintainability

The architecture should allow developers to add new business capabilities without introducing unnecessary coupling between the domain, application, infrastructure, and presentation layers.

### 4. Portfolio Demonstration

The project serves as a practical demonstration of full-stack enterprise development experience.

---

# Key Features

## Authentication

* Login
* Logout
* Access Token
* Refresh Token
* Token rotation
* Password hashing
* Password policies
* Account status
* Session management
* Authentication events

## User Management

* Create user
* Update user
* Delete/deactivate user
* User profile
* Assign roles
* Assign permissions
* Account activation/deactivation
* User search
* Pagination
* Filtering
* Sorting

## Organization Management

* Organization tree
* Parent/child relationships
* Departments
* Positions
* Employees
* Organizational hierarchy
* Organizational navigation
* Tree-based UI

## Role Management

* Create roles
* Update roles
* Delete roles
* Assign permissions
* Role-based authorization

## Permission Management

* Permission catalog
* Permission groups
* Role permissions
* User permissions
* Dynamic authorization
* Resource/action based permissions

Example:

```text
Users.Read
Users.Create
Users.Update
Users.Delete

Employees.Read
Employees.Create
Employees.Update
Employees.Delete

Organizations.Read
Organizations.Create
Organizations.Update
Organizations.Delete

AuditLogs.Read
Roles.Manage
Permissions.Manage
```

## Audit Logging

The platform records important security and business activities.

Example:

```text
User
Action
Entity
EntityId
Timestamp
IP Address
Request Path
HTTP Method
CorrelationId
TraceId
Changes
```

Example audit event:

```text
User: admin
Action: UPDATE
Entity: Employee
EntityId: 1052
IP: xxx.xxx.xxx.xxx
Timestamp: 2026-08-14T15:30:00Z
```

## Notifications

* In-app notifications
* Read/unread state
* Notification history
* User-specific notifications
* System notifications

## File Management

* Upload
* Download
* Delete
* File metadata
* File ownership
* File validation
* File size restrictions
* Extension restrictions

## Dashboard

The dashboard provides high-level operational information:

* Total users
* Active users
* Employees
* Departments
* Organizations
* Pending workflows
* Recent activities
* Notifications
* Audit events

## Advanced Search

The application supports:

* Keyword search
* Multi-field filtering
* Sorting
* Pagination
* Date ranges
* Status filtering
* Dynamic query parameters

---

# Domain

The main business domains are:

```text
Organization
Department
Employee
Position
User
Role
Permission
Workflow
AuditLog
Notification
File
```

Conceptually:

```text
Organization
    │
    ├── Department
    │      │
    │      ├── Employee
    │      │      │
    │      │      └── Position
    │      │
    │      └── Employee
    │
    └── Department

User
    │
    ├── Role
    │      │
    │      └── Permission
    │
    └── Employee
```

---

# Technology Stack

## Backend

| Technology            | Purpose              |
| --------------------- | -------------------- |
| .NET                  | Runtime              |
| ASP.NET Core          | REST API             |
| C#                    | Programming language |
| Entity Framework Core | ORM                  |
| SQL Server            | Relational database  |
| Redis                 | Distributed caching  |
| JWT                   | Authentication       |
| FluentValidation      | Request validation   |
| Serilog               | Structured logging   |
| Swagger / OpenAPI     | API documentation    |

## Frontend

| Technology       | Purpose              |
| ---------------- | -------------------- |
| Angular          | Frontend framework   |
| TypeScript       | Programming language |
| RxJS             | Reactive programming |
| Signals          | Reactive state       |
| Reactive Forms   | Form management      |
| Angular Material | UI components        |
| Bootstrap        | Layout / utilities   |

## DevOps

| Technology     | Purpose             |
| -------------- | ------------------- |
| Docker         | Containerization    |
| Docker Compose | Local orchestration |
| GitHub Actions | CI/CD               |
| GitHub         | Source control      |

---

# Architecture

The application follows a layered Clean Architecture approach.

```text
┌───────────────────────────────────────────┐
│                  Angular                  │
│        Presentation / UI / State          │
└─────────────────────┬─────────────────────┘
                      │
                      │ HTTPS / REST
                      ▼
┌───────────────────────────────────────────┐
│             ASP.NET Core API              │
│             Presentation Layer            │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
┌───────────────────────────────────────────┐
│              Application Layer            │
│       CQRS / Commands / Queries           │
│       Validation / DTOs / Behaviors       │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
┌───────────────────────────────────────────┐
│                Domain Layer               │
│ Entities / Value Objects / Events         │
│ Business Rules / Interfaces               │
└─────────────────────┬─────────────────────┘
                      │
                      ▼
┌───────────────────────────────────────────┐
│             Infrastructure                │
│ EF Core / SQL Server / Redis / Files      │
│ Authentication / External Services        │
└───────────────────────────────────────────┘
```

## Dependency Direction

Dependencies point toward the domain.

```text
Presentation
     ↓
Application
     ↓
Domain
     ↑
Infrastructure
```

The Domain layer does not depend on Infrastructure.

---

# Backend Architecture

The backend is organized into four primary projects.

```text
src/
├── EnterpriseManagement.Api
├── EnterpriseManagement.Application
├── EnterpriseManagement.Domain
└── EnterpriseManagement.Infrastructure
```

## Domain

Contains:

* Entities
* Value Objects
* Domain Events
* Domain Exceptions
* Business Rules
* Enumerations
* Repository abstractions

The Domain layer contains business logic and should remain independent of external frameworks whenever practical.

---

## Application

Contains:

* Commands
* Queries
* Handlers
* DTOs
* Validators
* Application Services
* Interfaces
* Behaviors
* Mapping
* Authorization abstractions

Example:

```text
CreateEmployeeCommand
        ↓
CreateEmployeeCommandHandler
        ↓
Employee Domain Model
        ↓
Repository
```

---

## Infrastructure

Contains implementations for:

* EF Core
* SQL Server
* Redis
* Repositories
* Authentication
* File storage
* Email
* External services
* Logging
* Persistence

---

## Presentation

Contains:

* Controllers
* Middleware
* Authentication configuration
* Authorization
* Exception handling
* API models
* Swagger/OpenAPI
* Dependency Injection configuration

---

# Frontend Architecture

The Angular application follows a feature-oriented structure.

```text
src/app/

├── core/
│   ├── authentication/
│   ├── authorization/
│   ├── interceptors/
│   ├── guards/
│   ├── services/
│   └── models/
│
├── shared/
│   ├── components/
│   ├── directives/
│   ├── pipes/
│   ├── validators/
│   └── ui/
│
├── features/
│   ├── auth/
│   ├── dashboard/
│   ├── organizations/
│   ├── departments/
│   ├── employees/
│   ├── users/
│   ├── roles/
│   ├── permissions/
│   ├── workflows/
│   ├── notifications/
│   ├── files/
│   └── audit-logs/
│
└── app.routes.ts
```

The frontend uses:

* Standalone Components
* Signals
* RxJS
* Reactive Forms
* Route Guards
* HTTP Interceptors
* Lazy Loading
* Reusable UI components
* Feature-based organization

---

# Project Structure

Recommended repository structure:

```text
enterprise-management-platform/
│
├── src/
│   ├── Backend/
│   │   ├── EnterpriseManagement.Api/
│   │   ├── EnterpriseManagement.Application/
│   │   ├── EnterpriseManagement.Domain/
│   │   └── EnterpriseManagement.Infrastructure/
│   │
│   └── Frontend/
│       └── enterprise-management-client/
│
├── tests/
│   ├── UnitTests/
│   ├── IntegrationTests/
│   ├── ApiTests/
│   └── FrontendTests/
│
├── docs/
│   ├── architecture.md
│   ├── database.md
│   ├── api.md
│   ├── security.md
│   ├── deployment.md
│   └── troubleshooting.md
│
├── ADR/
│   ├── 0001-clean-architecture.md
│   ├── 0002-cqrs.md
│   ├── 0003-authentication.md
│   ├── 0004-redis-caching.md
│   └── 0005-file-storage.md
│
├── docker/
│   ├── api/
│   ├── frontend/
│   └── sql-server/
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
│
├── docker-compose.yml
├── docker-compose.override.yml
├── .editorconfig
├── .gitignore
├── LICENSE
└── README.md
```

---

# Domain Model

Core entities:

```text
Organization
Department
Employee
Position
User
Role
Permission
Workflow
WorkflowInstance
AuditLog
Notification
File
RefreshToken
```

Example relationships:

```text
Organization
    │
    ├── Departments
    │       │
    │       └── Employees
    │               │
    │               └── Position
    │
    └── Departments

Employee
    └── User

User
    ├── Roles
    │      └── Permissions
    │
    └── Notifications
```

---

# Authentication & Authorization

Authentication is based on JWT.

```text
Client
   │
   │ Login
   ▼
ASP.NET Core
   │
   ├── Validate Credentials
   ├── Generate Access Token
   └── Generate Refresh Token
   │
   ▼
Client
```

## Access Token

The access token is used for API requests.

```http
Authorization: Bearer <access-token>
```

## Refresh Token

Refresh tokens are used to obtain new access tokens without forcing the user to log in again.

The implementation should support:

* Expiration
* Revocation
* Rotation
* Device/session tracking
* Secure storage

---

# Dynamic Permission System

Authorization is not hard-coded exclusively around roles.

The platform uses permissions such as:

```text
Users.Read
Users.Create
Users.Update
Users.Delete

Employees.Read
Employees.Create
Employees.Update
Employees.Delete

Organizations.Read
Organizations.Manage

Roles.Read
Roles.Manage

Permissions.Read
Permissions.Manage

AuditLogs.Read
```

This allows administrators to construct flexible authorization policies.

Example:

```text
Administrator
    ├── Users.*
    ├── Employees.*
    ├── Organizations.*
    └── AuditLogs.Read

HR Manager
    ├── Employees.Read
    ├── Employees.Create
    └── Employees.Update

Employee
    ├── Profile.Read
    └── Profile.Update
```

---

# Organization Management

The organization module supports hierarchical structures.

Example:

```text
Company
│
├── Engineering
│   ├── Backend
│   ├── Frontend
│   └── DevOps
│
├── Human Resources
│
├── Finance
│
└── Sales
```

The hierarchy is represented using parent-child relationships.

Example:

```text
Organization
    Id
    Name
    ParentId
```

The frontend provides a tree-based visualization for navigating organizational structures.

---

# Workflow

The workflow subsystem is designed to support configurable business processes.

Example:

```text
Employee
   │
   │ Submit Leave Request
   ▼
Pending
   │
   ▼
Manager Approval
   │
   ├── Rejected
   │
   └── Approved
          │
          ▼
        Completed
```

Potential workflow capabilities:

* Workflow definition
* Workflow states
* Workflow transitions
* Approvals
* Rejections
* Assignments
* Comments
* History
* Notifications

---

# Audit Logging

Audit logging is implemented as a first-class enterprise concern.

Important operations can produce audit events:

```text
CREATE
UPDATE
DELETE
LOGIN
LOGOUT
PASSWORD_CHANGE
ROLE_ASSIGNED
PERMISSION_CHANGED
FILE_UPLOADED
FILE_DELETED
```

Example:

```json
{
  "userId": "123",
  "action": "UPDATE",
  "entity": "Employee",
  "entityId": "456",
  "requestPath": "/api/employees/456",
  "method": "PUT",
  "correlationId": "...",
  "timestamp": "2026-08-14T15:30:00Z"
}
```

Audit records should be immutable from the application's normal business workflows.

---

# Notifications

Notifications are associated with users and system events.

Example:

```text
┌─────────────────────────────────┐
│ Notifications                   │
├─────────────────────────────────┤
│ Employee request approved       │
│ New workflow assigned           │
│ Role changed                    │
│ Password changed                │
└─────────────────────────────────┘
```

The architecture allows future integration with:

* Email
* Push notifications
* WebSockets
* SignalR

---

# File Management

The file subsystem manages:

* File metadata
* Upload
* Download
* Delete
* Ownership
* Content type
* File size
* Storage location

Example metadata:

```text
FileId
FileName
OriginalFileName
ContentType
Size
StoragePath
UploadedBy
CreatedAt
```

Storage implementation is abstracted behind an interface so that the application can later use:

```text
Local Storage
Azure Blob Storage
AWS S3
MinIO
```

without changing the domain layer.

---

# Caching

Redis is used for distributed caching.

Potential cache targets:

* User permissions
* Role permissions
* Organization tree
* Frequently accessed reference data
* Dashboard statistics

Example:

```text
API
 │
 ├── Redis Cache
 │
 └── SQL Server
```

Cache invalidation is performed when relevant data changes.

Example:

```text
Role Updated
     ↓
Permissions Changed
     ↓
Invalidate Role Cache
     ↓
Next Request
     ↓
Load Fresh Data
```

---

# API Design

The backend exposes RESTful APIs.

Example:

```text
/api/auth
/api/users
/api/roles
/api/permissions
/api/organizations
/api/departments
/api/employees
/api/positions
/api/workflows
/api/notifications
/api/files
/api/audit-logs
```

Example:

```http
GET    /api/employees
GET    /api/employees/{id}
POST   /api/employees
PUT    /api/employees/{id}
DELETE /api/employees/{id}
```

---

# Pagination

List endpoints support pagination.

Example:

```http
GET /api/employees?pageNumber=1&pageSize=20
```

Response:

```json
{
  "items": [],
  "pageNumber": 1,
  "pageSize": 20,
  "totalCount": 150,
  "totalPages": 8
}
```

---

# Filtering

Example:

```http
GET /api/employees?
    search=John&
    departmentId=5&
    isActive=true
```

---

# Sorting

Example:

```http
GET /api/employees?
    sortBy=lastName&
    sortDirection=asc
```

---

# Validation & Error Handling

The API uses centralized validation and exception handling.

Expected error response:

```json
{
  "type": "https://example.com/errors/validation",
  "title": "Validation failed",
  "status": 400,
  "errors": {
    "email": [
      "A valid email address is required."
    ]
  },
  "traceId": "..."
}
```

The API should use a consistent error contract across all endpoints.

---

# Database

Primary database:

```text
SQL Server
```

Entity Framework Core is used for:

* Entity mapping
* Relationships
* Migrations
* Transactions
* Querying
* Persistence

Database documentation is maintained in:

```text
docs/database.md
```

The database design includes:

* Primary keys
* Foreign keys
* Indexes
* Unique constraints
* Soft-delete strategy where appropriate
* Audit fields
* Concurrency considerations

Common audit fields:

```text
CreatedAt
CreatedBy
ModifiedAt
ModifiedBy
```

---

# Performance

Performance considerations include:

* Async I/O
* EF Core projections
* Pagination
* Database indexes
* Query optimization
* Redis caching
* Avoiding N+1 queries
* AsNoTracking for read-only queries
* Efficient filtering
* Lazy loading avoidance
* Proper connection management

Example:

```text
Client
  ↓
API
  ↓
Cache ────── HIT ──────> Response
  │
  MISS
  ↓
SQL Server
  ↓
Cache
  ↓
Response
```

---

# CQRS

The application separates reads and writes.

## Commands

Commands modify state.

Examples:

```text
CreateEmployeeCommand
UpdateEmployeeCommand
DeleteEmployeeCommand
AssignRoleCommand
AssignPermissionCommand
```

## Queries

Queries retrieve data.

Examples:

```text
GetEmployeeByIdQuery
GetEmployeesQuery
GetOrganizationTreeQuery
GetAuditLogsQuery
```

This separation makes business operations easier to reason about and test.

---

# Domain Events

Domain events are used to represent important business events.

Example:

```text
EmployeeCreated
EmployeeUpdated
EmployeeDeleted
RoleAssigned
PermissionChanged
WorkflowApproved
```

Example flow:

```text
Employee Created
      ↓
EmployeeCreated Domain Event
      ↓
Event Handler
      ├── Audit Log
      └── Notification
```

---

# SOLID Principles

The project applies SOLID principles throughout the architecture.

### Single Responsibility

Each class should have one clear responsibility.

### Open/Closed

The system should be extensible without unnecessary modification of existing business logic.

### Liskov Substitution

Abstractions should be safely replaceable by implementations.

### Interface Segregation

Interfaces should remain focused.

### Dependency Inversion

High-level business logic depends on abstractions rather than infrastructure implementations.

---

# Testing Strategy

Testing is divided into multiple levels.

```text
                 ┌───────────────┐
                 │  E2E / API    │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │ Integration   │
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │    Unit       │
                 └───────────────┘
```

## Unit Tests

Test:

* Domain logic
* Validators
* Command handlers
* Query handlers
* Authorization logic
* Services

## Integration Tests

Test:

* Database integration
* Repository behavior
* API pipeline
* Authentication
* Authorization

## API Tests

Test:

* HTTP endpoints
* Status codes
* Validation
* Authentication
* Authorization
* Response contracts

## Frontend Tests

Test:

* Components
* Services
* Validators
* Guards
* Interceptors
* User interactions

---

# Docker

Each major application component can be containerized.

```text
Angular Container
       │
       ▼
ASP.NET Core Container
       │
       ├──────────────► SQL Server
       │
       └──────────────► Redis
```

Example services:

```text
frontend
api
sqlserver
redis
```

---

# Docker Compose

Development infrastructure can be started using:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

View logs:

```bash
docker compose logs -f
```

Check running services:

```bash
docker compose ps
```

---

# CI/CD

GitHub Actions automates the development pipeline.

Example:

```text
Developer
   │
   ▼
Git Push
   │
   ▼
GitHub
   │
   ▼
GitHub Actions
   │
   ├── Restore
   ├── Build
   ├── Unit Tests
   ├── Integration Tests
   ├── Frontend Tests
   ├── Docker Build
   └── Security Checks
```

A production pipeline can additionally include:

```text
Build
  ↓
Test
  ↓
Docker Image
  ↓
Container Registry
  ↓
Deployment
```

---

# Security

Security is a core part of the architecture.

Implemented/planned security controls include:

* JWT authentication
* Refresh token rotation
* Password hashing
* Role-based authorization
* Permission-based authorization
* Resource-level authorization
* Input validation
* HTTPS
* CORS configuration
* Rate limiting
* Secure HTTP headers
* File upload validation
* Sensitive configuration through environment variables
* Secrets excluded from source control
* Audit logging

Sensitive values must never be committed to Git.

Example:

```text
ConnectionStrings
JWT Secret
Redis credentials
Storage credentials
External API keys
```

should be provided through environment configuration or a secret-management solution.

---

# Observability

The platform is designed with observability in mind.

Important telemetry includes:

```text
TraceId
CorrelationId
RequestPath
HTTP Method
Status Code
Elapsed Time
Client IP
User ID
Application
Thread ID
Process ID
```

Structured logging allows logs to be searched and correlated across services.

---

# Architecture Decision Records

Important architectural decisions are documented under:

```text
ADR/
```

Example:

```text
ADR/
├── 0001-clean-architecture.md
├── 0002-cqrs.md
├── 0003-jwt-authentication.md
├── 0004-redis-caching.md
├── 0005-file-storage.md
├── 0006-audit-logging.md
└── 0007-docker-deployment.md
```

Each ADR documents:

```text
Context
Decision
Alternatives
Consequences
```

This demonstrates not only implementation skills but also architectural decision-making.

---

# Documentation

Technical documentation is maintained under:

```text
docs/
```

Recommended documents:

```text
docs/
├── architecture.md
├── database.md
├── api.md
├── security.md
├── deployment.md
├── testing.md
└── troubleshooting.md
```

---

# Screenshots

Screenshots should demonstrate the major capabilities of the platform.

Recommended screenshots:

```text
docs/screenshots/
├── login.png
├── dashboard.png
├── organization-tree.png
├── employees.png
├── employee-form.png
├── users.png
├── roles.png
├── permissions.png
├── audit-logs.png
├── notifications.png
└── workflow.png
```

> Screenshots should focus on real application functionality rather than decorative UI.

---

# Architecture Diagram

The repository contains architecture documentation describing the complete system.

High-level architecture:

```text
                     ┌─────────────────────┐
                     │      Browser        │
                     │      Angular        │
                     └──────────┬──────────┘
                                │
                              HTTPS
                                │
                     ┌──────────▼──────────┐
                     │   ASP.NET Core API  │
                     │    REST / JWT       │
                     └──────────┬──────────┘
                                │
                     ┌──────────▼──────────┐
                     │    Application      │
                     │ CQRS / Validation  │
                     └──────────┬──────────┘
                                │
                     ┌──────────▼──────────┐
                     │       Domain        │
                     │ Business Rules      │
                     └──────────┬──────────┘
                                │
                     ┌──────────▼──────────┐
                     │   Infrastructure    │
                     └───────┬─────┬──────┘
                             │     │
                    ┌────────▼─┐ ┌─▼───────┐
                    │ SQLServer │ │  Redis  │
                    └───────────┘ └─────────┘
```

---

# Getting Started

## Prerequisites

Install:

* .NET SDK
* Node.js
* Angular CLI
* Docker Desktop
* Git

Verify:

```bash
dotnet --version
node --version
npm --version
docker --version
git --version
```

---

# Clone Repository

```bash
git clone https://github.com/<your-username>/enterprise-management-platform.git

cd enterprise-management-platform
```

---

# Run with Docker

Start the complete development environment:

```bash
docker compose up -d
```

Check containers:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs -f
```

Sinset-block-start:

```bash
docker compose down
```

---

# Run Backend Locally

Navigate to the API:

```bash
cd src/Backend/EnterpriseManagement.Api
```

Restore dependencies:

```bash
dotnet restore
```

Run:

```bash
dotnet run
```

---

# Run Frontend Locally

Navigate to the Angular application:

```bash
cd src/Frontend/enterprise-management-client
```

Install dependencies:

```bash
npm install
```

Run:

```bash
npm start
```

---

# Database Migrations

Create migration:

```bash
dotnet ef migrations add InitialCreate
```

Apply migration:

```bash
dotnet ef database update
```

---

# API Documentation

When running the application in development mode, Swagger/OpenAPI is available through the configured API documentation endpoint.

The API documentation covers:

* Authentication
* Users
* Roles
* Permissions
* Organizations
* Departments
* Employees
* Workflows
* Notifications
* Files
* Audit Logs

Detailed API documentation is maintained in:

```text
docs/api.md
```

---

# Development Workflow

Recommended workflow:

```text
1. Create Issue
       ↓
2. Create Feature Branch
       ↓
3. Implement
       ↓
4. Write Tests
       ↓
5. Run Local Validation
       ↓
6. Commit
       ↓
7. Pull Request
       ↓
8. CI Pipeline
       ↓
9. Code Review
       ↓
10. Merge
```

Branch naming:

```text
feature/user-management
feature/organization-tree
feature/dynamic-authorization

fix/refresh-token
fix/pagination-query

refactor/audit-service
```

---

# Environment Configuration

Environment-specific configuration should not be committed to source control.

Example:

```text
Development
Test
Staging
Production
```

Typical configuration:

```text
Database
Redis
JWT
CORS
Logging
File Storage
External Services
```

Secrets should be injected using:

```text
Environment Variables
GitHub Secrets
Azure Key Vault
AWS Secrets Manager
```

or an equivalent secure secret-management system.

---

# Roadmap

## Phase 1 — Foundation

* [x] Repository structure
* [x] Clean Architecture
* [x] Domain model
* [x] ASP.NET Core API
* [x] Angular application
* [x] SQL Server
* [x] Docker foundation

## Phase 2 — Authentication

* [ ] Login
* [ ] JWT
* [ ] Refresh Token
* [ ] Logout
* [ ] Session management
* [ ] Password policies

## Phase 3 — Organization

* [ ] Organization
* [ ] Department
* [ ] Position
* [ ] Employee
* [ ] Organization tree

## Phase 4 — Authorization

* [ ] User management
* [ ] Role management
* [ ] Permission management
* [ ] Dynamic authorization

## Phase 5 — Enterprise Features

* [ ] Audit logging
* [ ] Notifications
* [ ] File management
* [ ] Workflow
* [ ] Dashboard
* [ ] Advanced search

## Phase 6 — Performance

* [ ] Redis
* [ ] Query optimization
* [ ] Database indexing
* [ ] Caching strategy
* [ ] Performance testing

## Phase 7 — Quality

* [ ] Unit tests
* [ ] Integration tests
* [ ] API tests
* [ ] Angular tests
* [ ] Code coverage

## Phase 8 — DevOps

* [ ] Docker Compose
* [ ] GitHub Actions
* [ ] CI
* [ ] Docker image publishing
* [ ] CD
* [ ] Deployment documentation

---

# Engineering Principles

The project follows these principles:

### Clean Code

Code should be:

* Readable
* Testable
* Maintainable
* Explicit
* Consistent

### SOLID

Design should favor:

* Low coupling
* High cohesion
* Dependency inversion
* Focused abstractions

### Separation of Concerns

Each layer owns a clearly defined responsibility.

### Security by Design

Security is considered from the beginning rather than added at the end.

### Testability

Business logic should be testable independently of infrastructure.

### Observability

Production systems must be diagnosable through logs, metrics, tracing, and audit information.

### Automation

Build, test, and deployment processes should be automated whenever practical.

---

# Portfolio Value

This project is intentionally designed to demonstrate more than CRUD development.

It demonstrates practical experience with:

```text
Enterprise Architecture
        +
Backend Engineering
        +
Frontend Engineering
        +
Database Design
        +
Security
        +
Distributed Caching
        +
Testing
        +
Docker
        +
CI/CD
        +
Observability
```

The project demonstrates the ability to design and implement a complete enterprise system from domain modeling through deployment.

---

# What This Project Demonstrates

A reviewer should be able to see evidence of experience in:

* Designing enterprise applications
* Building REST APIs
* Designing relational databases
* Implementing authentication
* Implementing authorization
* Designing dynamic permission systems
* Building complex Angular applications
* Applying Clean Architecture
* Applying CQRS
* Using Entity Framework Core
* Using Redis
* Writing automated tests
* Containerizing applications
* Building CI/CD pipelines
* Handling application errors
* Implementing audit trails
* Designing scalable APIs
* Documenting architectural decisions

---

# Future Improvements

Potential future improvements include:

* SignalR real-time notifications
* Background job processing
* Message broker integration
* Distributed tracing
* OpenTelemetry
* Advanced reporting
* Elasticsearch
* Object storage
* Kubernetes deployment
* Cloud deployment
* Multi-tenancy
* Localization
* Feature flags
* Advanced workflow designer

---

# License

This project is intended as a portfolio and educational enterprise application.

Add the appropriate license before distributing the project publicly.

---

# Author

**Kamran Tajerbashi**

Software Engineer

This repository is part of a portfolio demonstrating modern enterprise application development with:

```text
.NET
ASP.NET Core
C#
Angular
TypeScript
SQL Server
Redis
Docker
GitHub Actions
```

---

## Final Architecture

```text
                         ENTERPRISE MANAGEMENT PLATFORM
                                      │
             ┌────────────────────────┼────────────────────────┐
             │                        │                        │
          Frontend                 Backend                 DevOps
             │                        │                        │
          Angular                ASP.NET Core              Docker
          TypeScript                 C#                 Docker Compose
          RxJS                       EF Core             GitHub Actions
          Signals                    CQRS
          Forms                      JWT
             │                        │
             └───────────────┬────────┘
                             │
                     ┌───────▼────────┐
                     │   Domain Layer │
                     │                │
                     │ Organization   │
                     │ Employee       │
                     │ User           │
                     │ Role           │
                     │ Permission     │
                     │ Workflow       │
                     │ AuditLog       │
                     └───────┬────────┘
                             │
                     ┌───────▼────────┐
                     │ Infrastructure │
                     │                │
                     │ SQL Server     │
                     │ Redis          │
                     │ File Storage   │
                     │ Logging        │
                     └────────────────┘
```

**Built as a production-oriented enterprise application, not just a CRUD demo.**
