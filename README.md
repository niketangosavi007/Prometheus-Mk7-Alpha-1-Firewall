# Prometheus-Mk7-Alpha-1-Firewall
# 🛡️ Prometheus NGF Mk7
### Next Generation Firewall | Linux Security Platform

**Version:** 1.1.0-dev  
**Codename:** Prometheus  
**Platform:** Linux (Kali Linux / Debian-based)  
**Firewall Backend:** nftables  
**Development Status:** Active Development

---

## 1. Overview

**Prometheus NGF Mk7** is a next-generation Linux firewall project designed to provide centralized firewall management, security monitoring, threat visibility, and controlled network enforcement.

Built around Python and the Linux `nftables` framework, Mk7 introduces a modular architecture combining firewall operations, system security monitoring, a REST API, and a web-based dashboard.

The objective is to develop a security platform that provides administrators with better visibility and control over their Linux system's network security.

## 2. Key Features

### 🔥 Firewall Management
- Native Linux nftables integration.
- Firewall initialization and status monitoring.
- Kernel firewall state inspection.
- Firewall rule management.
- IP quarantine management.
- Controlled firewall enforcement.

### 📊 Security Dashboard
- Web-based management interface.
- Real-time API health visibility.
- Firewall operational status.
- Security events and findings visibility.
- Centralized monitoring interface.

### 🔐 REST API Security
- Authorized firewall management endpoints.
- Token-based API authentication.
- Controlled access to firewall operations.
- Audit logging for security-related operations.

### 🖥️ System Monitoring
- Firewall service status.
- Antivirus status integration.
- Security sensor status monitoring.
- Kernel firewall state inspection.

### 🗄️ Audit & Data Management
- SQLite-based data storage.
- Security event persistence.
- Audit and operation tracking.
- Structured API responses.

## 3. Architecture

```text
             PROMETHEUS NGF Mk7
                      |
          +-----------+-----------+
          |                       |
     Web Dashboard           REST API
          |                       |
          |                Authentication
          |                       |
          +-----------+-----------+
                      |
              Core Service Layer
                      |
          +-----------+-----------+
          |           |           |
       Firewall    Monitoring    Audit
       Manager      Service      Store
          |           |           |
          |           |           |
       nftables   Antivirus     SQLite
       Backend     Sensors      Database
          |
      Linux Kernel
          |
     Network Security
```

## 4. Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Firewall Backend | nftables |
| Backend API | Flask / Python |
| Database | SQLite |
| Frontend | Web Dashboard |
| Authentication | Protected API Token |
| Service Management | systemd |
| Operating System | Linux |
| Network Security | Linux Netfilter |

## 5. Project Structure

The development architecture is organized into modular components:

```text
Prometheus-NGF-Mk7/
│
├── firewall.py
│   └── nftables firewall management
│
├── service.py
│   └── Firewall, antivirus and sensor status
│
├── api.py
│   └── REST API and authorized operations
│
├── dashboard/
│   └── Web-based management interface
│
├── data/
│   └── SQLite database
│
└── README.md
```

*Note: This is a conceptual overview of the main modules, not a verified complete repository tree.*

## 6. Development Configuration

Mk7 development uses a separate service configuration to avoid interfering with the existing Alpha 1.0 installation.

| Setting | Configuration |
|---|---|
| Development API Port | 8788 |
| Firewall Backend | nftables |
| Enforcement | Disabled by default |
| Database | Existing project database |
| Authentication | Existing protected token |
| Service Manager | Separate systemd service |

**Safety configuration:**

```bash
NGF_ALLOW_ENFORCEMENT=0
```

Firewall enforcement must remain disabled until firewall operations have been validated in a controlled environment.

## 7. Installation Requirements

Recommended dependencies:

- Linux operating system.
- Python 3.
- nftables.
- SQLite.
- systemd.
- Required Python project dependencies.

Install the system firewall dependency on Debian-based distributions:

```bash
sudo apt update
sudo apt install nftables python3 python3-venv sqlite3
```

Verify nftables availability:

```bash
sudo nft --version
sudo nft list ruleset
```

Run the application using its configured development service and environment.

## 8. Security Considerations

Prometheus NGF Mk7 is under active development.

- Firewall enforcement is disabled by default.
- Administrative operations require authorization.
- API access should remain restricted.
- Firewall changes must be tested before deployment.
- Avoid exposing the development API to untrusted networks.
- Preserve existing firewall rules and configurations before testing.

**Important:** Mk7 is not yet represented as a production-ready firewall or a fully autonomous threat prevention system.

## 9. Development Roadmap

| Version | Development Objective |
|---|---|
| Alpha 1.0 | Initial firewall platform and dashboard |
| Mk7 v1.1.0-dev | Modular nftables backend and API integration |
| Mk7 v1.2 | Extended firewall management and monitoring |
| Mk7 v1.3 | Improved threat detection and security analytics |
| Mk7 v2.0 | Advanced automated security and enforcement capabilities |

*Roadmap items are development objectives, not claims of completed functionality.*

## 10. Project Vision

The long-term vision of Prometheus NGF is to develop an intelligent Linux network security platform that combines:

- Next-generation firewall capabilities.
- Threat detection and security analytics.
- System-level security monitoring.
- Centralized security management.
- Controlled automated incident response.

The goal is to evolve Prometheus from a traditional firewall management project into a modular security platform.

## 11. Disclaimer

Prometheus NGF Mk7 is an independent cybersecurity research and development project.

It is intended for educational purposes, authorized security testing, and defensive system administration.

Use firewall enforcement features only in environments where you have permission to modify network security configurations.

---

**Developed by:** Niketan Gosavi  
**Project:** Prometheus NGF Mk7  
**Category:** Cybersecurity | Network Security | Linux Firewall Development
