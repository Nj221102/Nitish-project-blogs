---
layout: post
title: "SOB25: BOLT 12 and Greenlight Integration in Shopstr"
subtitle: "Non-custodial payment infrastructure development with BIP-353 username system"
date: 2025-05-15 09:00:00 -0400
author: Nitish Jha
tags: [sob25, bolt-12, greenlight, bip-353, shopstr, lightning-network]
comments: true
cover-img: /assets/img/bgimage.png
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/thumb.png
---

## Project Overview

**Institution:** Polaris School of Technology (Starex University)  
**Program:** B.Tech Computer Science (2nd Year, 2nd Semester)  
**Project Duration:** May 15 - August 15, 2025  

This project develops a non-custodial payment alternative to Shopstr's current Cashu payment system, enabling users to utilize Greenlight nodes for creating BOLT 12 offers linked to BIP-353 usernames (`user@shopstr.store`).

**Primary Objectives:**
1. Create DNS API for BIP-353 username registration with DNSSEC
2. Integrate Greenlight nodes for BOLT 12 offer generation  
3. Build user interface for username creation and management
4. Implement non-custodial payment infrastructure

---

## Technical Architecture

### Three-Tier System Architecture

**1. DNS Backend Implementation**
- **Framework:** TypeScript with Express.js
- **Queue System:** Redis Bull queue for asynchronous processing
- **DNS Provider:** Cloudflare DNS API  
- **Security:** DNSSEC enforcement, rate limiting, input validation
- **Monitoring:** Health checks, job status tracking, error handling
- **Integration:** Greenlight backend for BOLT 12 offer generation

**2. Greenlight Backend Integration**  
- **Framework:** Python (Flask/FastAPI)
- **Communication:** WebSocket for real-time updates
- **Caching:** Redis for node data and sessions
- **Authentication:** JWT token-based security

**3. Frontend UI Implementation**
- **Framework:** Next.js integration within Shopstr UI
- **Authentication:** GL Wallet with BIP-39 seed generation
- **Storage:** AES-256 encrypted localStorage for device credentials
- **Features:** Wallet dashboard, payment management, username registration

---

## Implementation Timeline

### Phase 1: DNS Infrastructure (May 15 - June 11)
**Weeks 1-2:** DNS Record Management API development
- POST endpoint for username/BOLT12/domain data
- Data validation and Cloudflare API integration
- Basic DNS record creation/update functionality

**Weeks 3-4:** DNSSEC Implementation  
- DNSSEC enforcement and verification
- Cloudflare API workflow completion
- Security authentication implementation

### Phase 2: Greenlight Backend (June 12 - July 9)
**Weeks 5-6:** Node Management Core
- BIP-39 seed-based node registration
- BOLT 12 offer generation for usernames
- `/register-username` endpoint implementation

**Weeks 7-8:** Payment Infrastructure
- Payment handling (send/receive) APIs
- DNS backend integration for username registration
- WebSocket real-time communication
- Redis caching implementation

**Mid-term Evaluation:** July 1-5, 2025

### Phase 3: Frontend Development (July 10 - August 6)
**Weeks 9-10:** Authentication Gateway
- BIP-39 seed phrase generation (client-side)
- Encrypted device credential storage
- GL Wallet login/signup interface

**Weeks 11-12:** Wallet Dashboard
- Payment initiation and receipt functionality
- BIP-353 username generation interface
- Real-time WebSocket updates
- JWT authentication integration

### Phase 4: Integration & Testing (August 7-15)
**Week 13:** Final Integration
- End-to-end system testing
- Bug fixes and optimization
- Final project documentation

---

## Technical Specifications

### DNS Backend API Structure

**Primary Endpoint:** POST /register-dns accepts username, domain, BOLT12 offer, and DNSSEC preference parameters. The system validates input data using comprehensive Joi schemas and queues the DNS registration request for asynchronous processing.

**Asynchronous Response Model:** Instead of blocking operations, the API immediately returns a unique job identifier with estimated completion time ranging from 2-5 minutes. This approach ensures scalability and prevents timeout issues during DNS propagation delays.

**Status Tracking System:** GET /status/{job_id} endpoint provides real-time monitoring of DNS registration progress. The system tracks job lifecycle from queued to processing to completed states, with detailed progress indicators and comprehensive result metadata including DNS record identifiers and completion timestamps.

### Greenlight Backend API Design

**Node Registration Endpoint:** POST /register-node processes BIP-39 seed phrases with optional passphrases for enhanced security. The system generates cryptographic node credentials while maintaining zero server-side storage of sensitive seed data.

**Username Registration Process:** POST /register-username creates unique Lightning Address-style identifiers by combining node identifiers with user-selected usernames and domain specifications. This endpoint integrates directly with the DNS backend for automated TXT record creation.

**Payment Processing Interface:** POST /pay endpoint facilitates Lightning Network transactions using BOLT 12 offers with specified amounts in millisatoshi units. The system provides comprehensive payment status tracking and error handling for failed transaction attempts.

### Security Implementation

**Authentication Methods:**
- **API Security:** Bearer token authentication with rate limiting
- **Cloudflare API:** Secure API key authentication with zone-level permissions
- **Backend Communication:** JWT token validation with Redis session management
- **WebSocket:** WSS encrypted connections with token-based authentication
- **Client Storage:** AES-256 encryption for device credentials

**DNSSEC Enforcement:**
- **Automated Verification:** DNSSEC verification integrated into queue processing
- **Multi-Resolver Validation:** 80% consensus across multiple DNS resolvers
- **Cryptographic Signatures:** DNS spoofing protection via DNSSEC signing chain
- **Production Monitoring:** Real-time DNSSEC status tracking and alerting
- DNS spoofing protection via cryptographic signatures
- Secure resolution of BIP-353 usernames

---

## Development Methodology

### Code Quality Standards
- **Testing:** Unit tests with >90% coverage
- **Documentation:** OpenAPI 3.0 specifications
- **Security:** Static analysis with security scanning
- **Performance:** Load testing and optimization

### System Integration Flow

**Multi-Stage Processing Pipeline:**
The system implements a sophisticated seven-stage workflow beginning with client-side BIP-39 seed generation and progressing through Greenlight node registration, BOLT 12 offer creation, and asynchronous DNS queue processing. Each stage includes comprehensive error handling and rollback mechanisms to ensure data consistency and user experience reliability.

**Enhanced Workflow Features:**
- **Non-blocking Operations:** Immediate API responses with comprehensive job tracking eliminate user wait times during DNS propagation delays
- **Progress Monitoring:** Real-time status updates provide granular completion percentages from initial request to final DNS record activation
- **Error Recovery:** Intelligent retry mechanisms with exponential backoff handle transient failures in DNS propagation and DNSSEC verification
- **Horizontal Scaling:** Distributed queue workers enable processing of thousands of concurrent DNS registrations across multiple server instances

### Frontend User Experience
- **Signup Flow:** BIP-39 seed display with security warnings
- **Login Flow:** Passphrase-based credential decryption
- **Dashboard:** Balance monitoring and payment interfaces
- **Username Management:** BIP-353 compliant address creation

---

## Academic and Professional Context

**Academic Institution:** Polaris School of Technology (Starex University)  
**Academic Level:** 2nd Year B.Tech Computer Science  
**Project Classification:** Summer of Bitcoin 2025 Contribution  

This project serves as both an academic capstone and a practical contribution to the Bitcoin Lightning Network ecosystem, demonstrating enterprise-grade development practices and protocol compliance standards.

**Contact Information:**  
- **Email:** nitishj221102@gmail.com  
- **LinkedIn:** [Nitish Jha](https://linkedin.com/in/nitish-jha-2b82aa155)  
- **GitHub:** [@Nj221102](https://github.com/Nj221102)  
- **Institution:** Polaris School of Technology

---

## DNS API Production Features

**TypeScript Architecture Benefits:**
- **Type Safety:** Comprehensive compile-time type checking eliminates runtime errors through strict interface definitions and type validation across all API endpoints and data structures.
- **Developer Experience:** Enhanced IDE support provides intelligent autocomplete, real-time error detection, and automated refactoring capabilities for improved development velocity.
- **Code Quality:** Self-documenting interfaces and type definitions create maintainable codebases with clear data contracts between system components.
- **Error Prevention:** Static type analysis catches potential bugs during development phase, reducing production issues and improving overall system reliability.

**Queue System Architecture:**
The Redis Bull Queue implementation provides enterprise-grade job processing with configurable retry mechanisms, exponential backoff strategies, and automatic job cleanup. The system maintains separate queues for different operation types while supporting distributed worker processes for horizontal scaling. Job persistence ensures reliability during system restarts, while comprehensive monitoring provides operational visibility into queue health and processing statistics.

**Security and Monitoring Framework:**
- **Rate Limiting:** IP-based request throttling prevents abuse with configurable time windows and request limits, ensuring fair resource allocation across all users.
- **Input Validation:** Comprehensive data sanitization using Joi schemas validates all incoming requests, preventing injection attacks and ensuring data integrity.
- **Health Monitoring:** Real-time system status verification checks Redis connectivity, Cloudflare API availability, and queue processing capacity with automated alerting for degraded services.
- **Error Tracking:** Structured logging with Winston provides detailed error tracking, performance metrics, and operational insights for production debugging and optimization.
- **API Authentication:** Bearer token validation ensures secure access control with session management and proper authorization handling across all endpoints.
