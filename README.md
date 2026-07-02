
<p align="center">
<img src="https://github.com/kongali1720/KongWallet-Payment-Gateway-API/blob/main/kop_surat.jpg" width="100%">
</p>

<p align="center">

---

<div align="center">

# 💳 KONGALI1720 Payment Gateway API 💳

### Secure • Fast • Multi-Payment • Merchant Ready

<p align="center">
<img src="https://raw.githubusercontent.com/kongali1720/KongWallet-Payment-Gateway-API/main/kongali-apigateway.png" width="100%">
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-API-000000?style=for-the-badge&logo=flask)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)

</p>

<p align="center">

![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?style=for-the-badge&logo=ubuntu)
![REST API](https://img.shields.io/badge/REST-API-blue?style=for-the-badge)
![HMAC](https://img.shields.io/badge/HMAC-SHA256-success?style=for-the-badge)
![Webhook](https://img.shields.io/badge/Webhook-Supported-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

</p>

---

### Modern Payment Gateway Backend for Crypto, Card, Bank Transfer & Fiat Payments

</div>

---

# 📦 Features

- 🔐 HMAC Authentication
- ⚡ RESTful API
- 💳 Card Payment
- ₿ Crypto Payment
- 🏦 SWIFT Bank Transfer
- 💵 Fiat Payment
- 📡 Webhook Notification
- 🔄 Transaction Monitoring
- 📈 Live Crypto Price
- 🚀 Redis Cache
- 🛡 Rate Limiting
- 📜 Merchant Management
- 📊 Dashboard
- 📝 Transaction Logging

---

# 🏗 Project Structure

```text
/opt/kongwallet-api/
├── run.py
├── requirements.txt
├── config/
│   ├── __init__.py
│   └── settings.py
├── api/
│   ├── __init__.py
│   ├── extensions.py
│   ├── middleware/
│   │   ├── auth.py
│   │   └── rate_limit.py
│   ├── models/
│   │   ├── transaction.py
│   │   ├── merchant.py
│   │   └── webhook_log.py
│   ├── routes/
│   │   ├── transactions.py
│   │   ├── crypto.py
│   │   └── webhooks.py
│   └── services/
│       ├── crypto/
│       ├── card/
│       ├── swift/
│       ├── fiat/
│       └── price/
├── dashboard/
├── logs/
├── .env
└── kongwallet.service
```

```mermaid
flowchart LR

Merchant --> API

API --> Auth
API --> RateLimit

Auth --> Transaction

Transaction --> Crypto
Transaction --> Card
Transaction --> SWIFT
Transaction --> Fiat

Crypto --> Blockchain
Card --> Stripe
SWIFT --> Bank
Fiat --> LocalBank

Blockchain --> Database
Stripe --> Database
Bank --> Database
LocalBank --> Database

Database --> Webhook

Webhook --> Merchant
```

```mermaid
graph TB

A[Merchant Application]

subgraph API Layer
B[REST API]
C[Authentication]
D[Rate Limiter]
end

subgraph Business Logic
E[Transaction Service]
F[Payment Service]
G[Price Service]
end

subgraph Payment Providers
H[Blockchain]
I[Stripe]
J[SWIFT]
K[Fiat Bank]
end

subgraph Storage
L[(PostgreSQL)]
M[(Redis)]
N[(Logs)]
end

A --> B

B --> C
B --> D

C --> E
D --> E

E --> F
E --> G

F --> H
F --> I
F --> J
F --> K

F --> L
G --> L

E --> M

L --> N
```

```mermaid
sequenceDiagram

participant Merchant

participant API

participant Payment

participant Database

participant Webhook

Merchant->>API: Create Transaction

API->>Database: Save Pending

API->>Payment: Generate Payment

Payment-->>API: Payment Address

API-->>Merchant: Payment URL

Payment->>Database: Payment Confirmed

Database->>Webhook: Send Notification

Webhook-->>Merchant: Transaction Success
```

## Project Tree
```text
kongwallet-api/
│
├── api/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── services/
│
├── config/
├── dashboard/
├── logs/
├── requirements.txt
├── run.py
└── kongwallet.service
```

## Server Preparations

```bash
# Create Project Directory
mkdir -p /opt/kongwallet-api
cd /opt/kongwallet-api

# Create Application Structure
mkdir -p api/routes api/models api/middleware api/services/crypto
mkdir -p api/services/card api/services/swift api/services/fiat
mkdir -p api/services/price dashboard/static/img dashboard/templates
mkdir -p config logs
```

---

# 💳 Supported Payment

| Method | Status |
|---------|--------|
| Crypto | ✅ |
| Visa / Mastercard | ✅ |
| SWIFT Transfer | ✅ |
| Fiat | ✅ |
| Merchant API | ✅ |
| Webhook | ✅ |

---

# 🔐 Security

- HMAC SHA256 Authentication
- API Key Verification
- Rate Limiter
- Redis Session
- Secure Webhook
- Request Signature
- Environment Variables
- HTTPS Ready

---

# ⚙ Technology Stack

- Python
- Flask
- PostgreSQL
- Redis
- SQLAlchemy
- Gunicorn
- Nginx
- Linux
- Docker

---

# 🚀 Installation

```bash
sudo apt update

sudo apt install -y \
python3.11 \
python3.11-venv \
python3-pip \
nginx \
certbot \
python3-certbot-nginx \
postgresql \
postgresql-contrib \
redis-server
```

```bash
git clone https://github.com/kongali1720/kongwallet-api.git

cd kongwallet-api

python3 -m venv venv

source venv/bin/activate

pip install -r requirements.txt
```

## Python3 Environment 

```bash
cd /opt/kongwallet-api

python3.11 -m venv venv

source venv/bin/activate

pip install --upgrade pip

pip install flask
pip install flask-sqlalchemy
pip install flask-cors
pip install flask-limiter

pip install psycopg2-binary
pip install redis
pip install requests
pip install python-dotenv

pip install gunicorn
pip install stripe
pip install cryptography
```

Run

```bash
python run.py
```

---

# 📡 API Modules

```
Transactions API
Crypto API
Card API
SWIFT API
Fiat API
Merchant API
Webhook API
Price API
```

## Road Map

```mermaid
timeline

title KongWallet Roadmap

2026 Q3

: REST API

: Merchant Dashboard

: Webhook

2026 Q4

: Crypto Wallet

: Stripe

: SWIFT

2027

: Multi-chain

: Admin Panel

: API Analytics

: Kubernetes Support
````

```mermaid
timeline
title KongWallet Development Roadmap

2026 Q3
: Core API
: Merchant API
: PostgreSQL
: Redis

2026 Q4
: Stripe Integration
: Crypto Wallet
: Webhook Engine

2027 Q1
: Admin Dashboard
: Analytics
: Multi-chain

2027 Q2
: Multi Currency
: Kubernetes
: High Availability
```

---
# 📊 Payment Flow

<p align="center">
<img src="https://raw.githubusercontent.com/kongali1720/KongWallet-Payment-Gateway-API/main/kongali-apigateway.png" width="100%">
</p>

---

# 📊 Payment Processing Flow

The following diagram illustrates the complete lifecycle of a payment transaction within the KongWallet Payment Gateway ecosystem. Every request passes through authentication, payment processing, verification, persistent storage, and webhook delivery before reaching the merchant application.

```mermaid
flowchart LR

    A([🛒 Merchant]) -->|Create Payment| B[🌐 KongWallet API]

    B --> C{🔐 Authentication}

    C -->|Valid API Key| D[⚡ Rate Limiter]

    C -->|Invalid| X([❌ Request Rejected])

    D --> E[📦 Create Transaction]

    E --> F{💳 Payment Method}

    F --> G[₿ Crypto]

    F --> H[💳 Card]

    F --> I[🏦 SWIFT]

    F --> J[💵 Fiat]

    G --> K[⚙ Payment Processor]
    H --> K
    I --> K
    J --> K

    K --> L[🔍 Verification Engine]

    L --> M[(🗄 PostgreSQL)]

    M --> N[📡 Webhook Service]

    N --> O([🖥 Merchant Server])

    style A fill:#2ecc71,color:#fff
    style B fill:#3498db,color:#fff
    style C fill:#9b59b6,color:#fff
    style D fill:#f39c12,color:#fff
    style E fill:#16a085,color:#fff
    style F fill:#34495e,color:#fff
    style K fill:#e67e22,color:#fff
    style L fill:#8e44ad,color:#fff
    style M fill:#2c3e50,color:#fff
    style N fill:#d35400,color:#fff
    style O fill:#27ae60,color:#fff
    style X fill:#c0392b,color:#fff
```

# 📄 License

MIT License

---

<div align="center">

Made with ❤️ by **KongWallet**

</div>

<div align="center">


# ☕ Support Development


Jika project ini membantu kamu,
support kecil sangat berarti.


<a href="https://www.paypal.com/paypalme/bungtempong99/">

<img src="https://img.shields.io/badge/BUY_ME_A_COFFEE-support-yellow?style=for-the-badge&logo=buymeacoffee">

</a>


</div>
