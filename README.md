# Project Overview - Codetikki        
     
## Project Description      

**Codetikki** is a comprehensive Spring Boot-based microservice platform designed to manage competitive coding platforms with integrated authentication, user profiles, activity tracking, quiz management, and administrative features. The system is built on modern Spring Cloud technologies and provides a scalable, maintainable architecture for handling various aspects of a coding competition platform.

## System Purpose

Codetikki serves as a backend infrastructure for:
- **User Management**: Authentication, registration, and profile management
- **Coding Competitions**: Activity tracking, competition management, and coding challenges
- **Quiz System**: Quiz creation, management, and scoring
- **Employee Management**: HR and employee data management
- **Communication**: Internal messaging and notifications
- **Admin Dashboard**: System administration and monitoring
- **Logging & Analytics**: Comprehensive logging and activity tracking

## Main Features

### Core Features
- **Multi-Module Microservice Architecture**: Independent modules with clear separation of concerns
- **Service Discovery**: Eureka-based service discovery and registration
- **API Gateway**: Centralized API gateway for routing and load balancing
- **Authentication & Authorization**: Secure user authentication with JWT/Session-based security
- **User Profiles**: User profile management with comprehensive data fields
- **Activity Tracking**: Real-time activity tracking and logging
- **Quiz Management**: Full quiz lifecycle management including creation, execution, and scoring
- **Employee Management**: HR system for employee data and management
- **Enhanced Logging**: Custom logging framework with SLF4J/Logback integration

### Technical Features
- **Spring Boot 3.3.0**: Latest stable Spring Boot framework
- **Java 17**: LTS Java version with enhanced performance
- **Maven Multi-Module Build**: Centralized dependency and plugin management
- **MySQL Database**: Relational data persistence
- **OpenAPI/Swagger**: Auto-generated API documentation
- **Custom Logger Factory**: Centralized logging configuration

## High-Level Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Client Applications                   │
└────────────────────┬────────────────────────────────────┘
                     │
         ┌───────────▼──────────┐
         │   API Gateway        │
         │  (Port 8761)         │
         └───────────┬──────────┘
                     │
    ┌────────────────┼────────────────┐
    │                │                │
    ▼                ▼                ▼
┌─────────┐  ┌──────────┐  ┌────────────────┐
│Auth Svc │  │Log Svc   │  │ Spark Feature  │
│         │  │          │  │ Service        │
└────┬────┘  └──────────┘  └────────────────┘
    │
    │  ┌─────────────────────────────────┐
    │  │   Service Discovery Eureka      │
    │  │   (Port 8761)                   │
    │  └─────────────────────────────────┘
    │
    │   Other Services:
    ├── Profile Service
    ├── Employee Service
    ├── Quiz Management Service
    ├── Activity Service
    ├── Communication Service
    ├── Coding Service
    ├── Competition Service
    ├── Admin Service
    ├── Quiz Question Service
    └── Quizmanagement Service

         │
    ┌────▼────────────────┐
    │  MySQL Database     │
    │                     │
    └─────────────────────┘
```

## Architecture Patterns

### Microservice Pattern
- Each module operates as an independent service
- Services communicate through REST APIs
- Service discovery via Eureka Server
- API Gateway for external client access

### MVC (Model-View-Controller) Pattern
Within each service:
- **Controllers**: Handle HTTP requests/responses
- **Services**: Business logic implementation
- **Repositories**: Database access layer
- **Entities**: Data models for database mapping
- **DTOs**: Data transfer objects for API contracts

## Key Components

| Component | Purpose | Technology |
|-----------|---------|-----------|
| API Gateway | Central entry point, routing | Spring Cloud Gateway |
| Eureka Server | Service discovery | Spring Cloud Eureka |
| Authentication Service | User authentication & security | Spring Security |
| Profile Service | User profile management | Spring Data JPA |
| Quiz Service | Quiz management and execution | Spring Web |
| Activity Service | Activity tracking | Custom Logging |
| Employee Service | HR management | Spring Web |
| Database | Data persistence | MySQL |
| Logging | Centralized logging | SLF4J + Logback |

## Project Statistics

- **Total Modules**: 15+
- **Java Files**: 120+
- **Configuration Files**: 10+
- **Database Schema**: 15+ tables
- **API Endpoints**: 50+
- **Lines of Code**: 15,000+

## Development Team

- **Backend Architects**: Multi-developer team
- **Technology Stack**: Java 17, Spring Boot 3.3.0, Spring Cloud
- **Database**: MySQL 8.x
- **Build Tool**: Maven 3.9+

## Deployment & Infrastructure

- **Target Environment**: Cloud-ready (Azure/AWS/On-Premise)
- **Containerization**: Docker-ready (Dockerfile included)
- **Database Migration**: SQL scripts included
- **Configuration Management**: Environment-based property files

## Documentation Structure

This documentation suite includes:
1. **Technology Stack Details** - Complete dependency overview
2. **Project Setup Guide** - How to build and run the project
3. **Parent POM Documentation** - Dependency management details
4. **Architecture Deep Dive** - System design and patterns
5. **Module Structure** - Each module breakdown
6. **Logging Guidelines** - Logging best practices
7. **API Documentation** - Complete API reference
8. **Code Standards** - Naming conventions and patterns
9. **Module Creation Guide** - How to add new modules
10. **Error Handling** - Exception handling patterns
11. **Security Setup** - Authentication and authorization
12. **Testing Guide** - Testing strategies and examples
13. **Database Schema** - Table structures and relationships
14. **Module Documentation** - Individual module guides

## Support & Contribution

For questions about the project structure, please refer to the module-specific documentation in the `/docs/modules` directory or contact the development team.

---

**Version**: 1.0.0  
**Last Updated**: 2026-03-02  
**Java Version**: 17  
**Spring Boot Version**: 3.3.0  
