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
- **Framework:** Node.js with Express.js
- **DNS Provider:** Cloudflare DNS API  
- **Security:** DNSSEC enforcement and verification
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

**Endpoint:** `POST /register-dns`
```json
{
  "username": "user",
  "domain": "shopstr.store", 
  "bolt12_offer": "lno1...",
  "dnssec_enabled": true
}
```

**Response (Success):**
```json
{
  "status": "success",
  "message": "DNS record created successfully",
  "dns_record": {
    "name": "user.shopstr.store",
    "type": "TXT",
    "content": "bitcoin:lno1...",
    "ttl": 300
  }
}
```

### Greenlight Backend API Design

**Node Registration:** `POST /register-node`
```json
{
  "seed_phrase": "abandon abandon abandon...",
  "passphrase": "optional_passphrase"
}
```

**Username Registration:** `POST /register-username`  
```json
{
  "node_id": "03a1b2c3...",
  "username": "alice",
  "domain": "shopstr.store"
}
```

**Payment Processing:** `POST /pay`
```json
{
  "node_id": "03a1b2c3...",
  "bolt12_offer": "lno1...",
  "amount_msat": 100000
}
```

### Security Implementation

**Authentication Methods:**
- Cloudflare API: Secure API key authentication
- Backend Communication: JWT token validation
- WebSocket: WSS encrypted connections
- Client Storage: AES-256 encryption for device credentials

**DNSSEC Enforcement:**
- Automated DNSSEC verification on domain registration
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
```
1. User creates BIP-39 seed → Client-side generation
2. Node registration → Greenlight backend
3. Username selection → BOLT 12 offer generation  
4. DNS registration → Cloudflare API integration
5. Real-time updates → WebSocket notifications
```

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
