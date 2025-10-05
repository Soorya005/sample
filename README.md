#  BridgeAI

![License](https://img.shields.io/badge/License-MIT-green) ![Python](https://img.shields.io/badge/Python-3.11-blue) ![Docker](https://img.shields.io/badge/Docker-Container-blue) ![Hackathon](https://img.shields.io/badge/Hackathon-FutureStack25-purple)

An **Online-First AI Assistant with Automatic Offline Fallback**.  
BridgeAI is a hybrid AI assistant that prioritizes fast cloud AI (Cerebras) when internet is available, and seamlessly falls back to a local model when the connection drops — ensuring you never lose access to AI assistance.

**Built by Team Cyber_Samurais for WeMakeDevs FutureStack GenAI Hackathon 2025**

---

##  Problem We Solve
- Traditional AI assistants fail when internet drops   
- BridgeAI automatically switches to a local model  
- Perfect for:  
  -  Remote/rural areas with unreliable internet  
  -  Traveling (airplane mode)  
  -  Privacy-sensitive tasks  
  -  Cost-conscious users  
  -  Critical applications (healthcare, emergency services)

---

##  Key Features
-  Online-First: Fast cloud AI (Cerebras llama-3.3-70b) when connected  
-  Automatic Fallback: Seamlessly switches to local model offline  
-  Zero Manual Switching: Auto network detection  
-  Docker Containerized: One-command setup, professional deployment  
-  MCP Gateway: Smart routing between offline & online layers  
-  Always Responsive: Never “No connection” errors  
-  Fully Functional Offline Mode for privacy  

---

##  Architecture Overview

Mermaid system flow diagram:

```mermaid
flowchart TD
    A[User Query] --> B[MCP Gateway]
    B -->|Online Available| C[Cerebras API]
    B -->|Offline| D[LLaMA Local Model]
    C --> E[Response & Metadata Logged]
    D --> E[Response & Metadata Logged]
    E --> F[User Receives Answer]
For detailed architecture & workflow, see ARCHITECTURE.md

 Technology Stack
Frontend: React + Vite, TailwindCSS, Lucide Icons
Backend: FastAPI, llama-cpp-python, Cerebras Cloud SDK
Gateway: Custom MCP Gateway (Model Context Protocol)
Infrastructure: Docker + Docker Compose, Microservices

 Quick Start
See QUICKSTART.md for installation and setup instructions.

 Use Cases
 Remote/Rural Areas – Limited connectivity

 Travel – Offline knowledge assistant

 Healthcare – Privacy-sensitive environment

Education – Rural schools or offline curriculums

Enterprise – Air-gapped networks

Contributing
See CONTRIBUTING.md for contribution guidelines.

 License
MIT License – see LICENSE for details
