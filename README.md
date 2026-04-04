⚠️ Project Status: In Progress (Rebuild)

This project is currently being **restructured and rebuilt with a new technology stack**.  
The previous implementation has been archived.  
This repository remains the central reference for architecture, service design, and DevOps-related decisions.

# Online Reservation – Project Overview

This repository serves as the **central overview** for my portfolio project **Online Reservation**.  
It describes the project goals, architecture, approach, and current development status, and links to the related code repositories.

The project is intentionally in a **work-in-progress** state and is being developed incrementally.

---

## Overview

Online Reservation is a **service-oriented web application** for two distinct user groups:

- **Customers** who want to book appointments  
- **Businesses** (e.g. hair salons, massage studios, nail studios) that manage services, staff, and bookings  

The focus of this project is not only on functionality, but primarily on:

- architectural decisions  
- clear separation of responsibilities  
- realistic development and release cycles  
- quality assurance and deployment strategies  

---

## Architecture – current state

The application is modular and consists of the following core components:

### Auth Service (Java / Jakarta EE)
A standalone backend service responsible for:
- login and authentication  
- JWT-based tokens  
- role model (**Role Based Access Control – RBAC**)  
- implemented using:
  - **Java 21**
  - **Jakarta EE (JAX-RS, CDI)**
  - **JPA / Hibernate**
  - **Maven**
  - **WildFly**

---

### Central Backend (planned)
A shared API for business and customer functionality, planned as a separate service:

- business modules  
- customer modules  
- booking modules  

including:
- **RBAC**
- **tenant checks** (access only within the context of the associated business)

**Status:** TBA

---

### Frontend (implemented incrementally)

- **Current:** very simple HTML-based UI to validate API flows  
- **Planned:** migration to **Angular (TypeScript)** with role-based navigation  

---

### Database

- **PostgreSQL**
- containerized for local development

---

### DevOps & Infrastructure

- **Docker** for containerization  
- **docker compose** for local setup  
- **Maven** for build and dependency management  
- **Jenkins (planned)** for CI pipelines  
- **Kubernetes (target environment)**  
- **Helm (planned)** for deployments  

---

The architecture is designed to enable **early releases**, while keeping later extensions (e.g. UI framework changes or further service separation) conceptually prepared.

---

## Multi-tenancy

Multi-tenancy is implemented on **multiple layers**:

- **Application layer:**  
  - Role Based Access Control (RBAC)  
  - tenant checks (e.g. `business_id` / `tenant_id`)

- **Platform layer (target environment):**  
  - Kubernetes deployment with **namespaces per tenant**  
  - separation of configuration, resources, and deployments  

---

## Development & target environment

### Local development

- Docker-based containers  
- orchestration via **docker compose**  
- reproducible development environment  
- realistic service setup already during local development  

---

### Target environment

- deployment to a **Kubernetes cluster**  
- Docker images and configurations are prepared from the beginning  
- Kubernetes is **not required for early releases**, but clearly defined as the target platform  

---

## Release strategy

The project is developed **incrementally**.  
The full feature set is delivered across multiple releases.

---

### Release 1 – MVP (intentionally reduced)

**Auth**
- login with username / password  
- no customer self-registration  
- focus on technical fundamentals (JWT, roles, access)  

**Backend / API**
- creation of a business entity  
- maintenance of a simple schedule (free / occupied time slots)  
- creation of customers by the business  
- appointment booking within available slots  
- no complex business rules  

**Frontend**
- very simple HTML-based UI  
- focus on functionality rather than UI design  

---

The goal of this release is a **stable end-to-end flow**, not a fully featured product.

---

## Planned future releases (outlook)

- migration of the frontend to **Angular (TypeScript)**  
- customer self-registration  
- login via **OAuth / OIDC**  
- extension of booking and role models  
- improved validation and business logic  
- integration of **Jenkins CI pipelines**  
- Kubernetes deployment with Helm  

---

## CI/CD & quality assurance

Planned and incrementally implemented:

- Docker-based containerization of all components  
- **Jenkins pipelines** for:
  - build (`mvn package`)  
  - automated tests  
  - container image build  
- clear separation of:
  - code quality  
  - tests  
  - build steps  

The pipeline is designed to support both local development and later Kubernetes deployments.

---

## Target vision

In its final stage, the application is intended to:

- provide two clearly separated user experiences (business / customer)  
- offer a clean and extensible backend architecture  
- use modern authentication and authorization mechanisms  
- run containerized and orchestrated on Kubernetes  
- reflect real-world development, release, and operational processes  

---

## Repositories

- **Project Overview:**  
  https://github.com/RubinaWeinzettl/online-reservation-overview  

- **Auth Service (Java):**  
  https://github.com/RubinaWeinzettl/online-reservation-auth-java  

- **API:**  
  TBA  

- **Web:**  
  https://github.com/RubinaWeinzettl/online-reservation-web  
