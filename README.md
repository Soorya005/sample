# BridgeAI

[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE) [![Python](https://img.shields.io/badge/Python-3.11-blue)]() [![Docker](https://img.shields.io/badge/Docker-Container-blue)]() [![Hackathon](https://img.shields.io/badge/Hackathon-FutureStack25-purple)]()

**BridgeAI** is an online-first AI assistant with automatic offline fallback. It prioritizes fast cloud AI (Cerebras) when internet is available, and seamlessly switches to a local model when the connection drops, ensuring continuous access to AI assistance.

**Developed by Team Cyber_Samurais for WeMakeDevs FutureStack GenAI Hackathon 2025**

---

## Problem Statement

Traditional AI assistants fail when internet connectivity is lost. BridgeAI addresses this issue by automatically switching to a local model.  

Applicable scenarios:
- Remote or rural areas with unreliable internet  
- Travel or airplane mode  
- Privacy-sensitive tasks  
- Cost-conscious users  
- Critical applications in healthcare or emergency services  

---

## Key Features

- Online-first operation using Cerebras llama-3.3-70b when connected  
- Automatic offline fallback using LLaMA local model  
- No manual switching required; network detection is automatic  
- Docker containerized for easy setup and deployment  
- MCP Gateway for intelligent routing between offline and online layers  
- Caching and metadata logging for improved offline functionality  

---

## Architecture & Workflow

### System Flowchart

```mermaid
flowchart TD
    A[User Query] --> B[MCP Gateway]
    B -->|Online Available| C[Cerebras API]
    B -->|Offline| D[LLaMA Local Model]
    C --> E[Response & Metadata Logged]
    D --> E[Response & Metadata Logged]
    E --> F[User Receives Answer]
Sequence Overview
User submits a query, which is received by the MCP Gateway

MCP Gateway determines whether the system is online or offline

Online: Cerebras API handles the query

Offline: LLaMA local model handles the query

Response and metadata are logged, then returned to the user

For detailed architecture and workflow, see ARCHITECTURE.md.

Technology Stack
Frontend: React + Vite, TailwindCSS, Lucide Icons

Backend: FastAPI, llama-cpp-python, Cerebras Cloud SDK

Gateway: Custom MCP Gateway (Model Context Protocol)

Infrastructure: Docker + Docker Compose, Microservices

Quick Start
Refer to QUICKSTART.md for installation and setup instructions.

Use Cases
Remote or rural areas with limited connectivity

Offline knowledge assistant during travel

Privacy-sensitive environments in healthcare

Education in offline or rural setups

Enterprise environments with air-gapped networks

Contributing
See CONTRIBUTING.md for guidelines on contributing to this project.

License
MIT License – see LICENSE for details

Team Cyber_Samurais
Developed for WeMakeDevs FutureStack GenAI Hackathon 2025.
Acknowledgments: Cerebras, Meta (LLaMA), Docker, FastAPI & React communities.

pgsql
Copy code
