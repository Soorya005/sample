# BridgeAI

**An Online-First AI Assistant with Automatic Offline Fallback**

---

## The Problem We Solve

Ever had an AI assistant fail because your internet dropped? **BridgeAI solves this.**

- Traditional AI: Breaks when internet fails ❌
- BridgeAI: Automatically switches to local model ✅

Perfect for:
- Remote/rural areas with unreliable internet
- Working while traveling (airplane mode)
- Privacy-sensitive tasks (use offline mode)
- Cost-conscious users (reduce API costs)
- Critical applications (healthcare, emergency services)

---

## Key Features

- Online-First: Fast cloud AI (Cerebras llama-3.3-70b) when connected
- Automatic Fallback: Seamlessly switches to local model when internet drops
- Zero Manual Switching: Detects network changes automatically
- Docker Containerized: Professional deployment, one-command setup
- MCP Gateway: Smart routing layer using Model Context Protocol
- Privacy Option: Fully functional offline mode (data stays local)
- Always Responsive: Never shows "No connection" errors

---

## Quick Start

### For Hackathon Judges
**[See FOR_JUDGES.md for complete testing guide](FOR_JUDGES.md)**

### Quick Setup (Windows)

```bash
# Clone repository
git clone https://github.com/YourUsername/BridgeAI.git
cd BridgeAI

# Build and start all services
docker-compose up --build
Architecture
graph TD
    %% User Interaction
    A[User Sends Question] --> B[BridgeAI Receives Request]

    %% Network Detection
    B --> C[Check Internet Connection]

    %% Decision: Online or Offline
    C --> D{Internet Available?}
    D -- Yes --> E[Send Request to MCP Gateway]
    D -- No --> F[Route Request to Local Model]

    %% MCP Gateway Flow
    E --> G[Cloud AI (Cerebras llama-3.3-70b)]
    G --> H[Process Response]
    H --> I[Send Response Back to User]

    %% Local Model Flow
    F --> J[Local AI Model (Offline)]
    J --> K[Process Response]
    K --> I

    %% Docker and Deployment
    subgraph Docker Setup
        B
        C
        E
        F
    end

    style Docker Setup fill:#f9f,stroke:#333,stroke-width:2px

What's Included

3 Dockerfiles (Frontend, Backend, Gateway)

docker-compose.yml - Orchestrates all services

Frontend: React + TailwindCSS + Vite

Backend: FastAPI + llama-cpp-python + Cerebras SDK

Gateway: MCP (Model Context Protocol)

Use Cases

Perfect for:

Remote/Rural Areas - Limited internet connectivity

Traveling - Use offline mode seamlessly

Privacy-Conscious - Keep data local

Hybrid Work - Always responsive AI

System Requirements
Minimum

Docker Desktop installed (Windows, Linux, macOS)

At least 8GB RAM

2 CPU cores minimum

Testing Network Switching

Start the app with internet connection

Send a message → Uses Cerebras (fast response)

Disable WiFi/Internet

Send another message → Automatically switches to Local Model

Re-enable internet → Switches back to Cerebras

Previous offline messages auto-enhance

No manual toggle needed!

Commands
# Start application
docker-compose up --build

# Stop application
docker-compose down

# Rebuild a specific service
docker-compose up --build <service_name>

Contributing

We welcome contributions! Please see CONTRIBUTING.md
 for details.

License

This project is licensed under the MIT License - see LICENSE
 for details.

Team Cyber_Samurais

Built for WeMakeDevs FutureStack GenAI Hackathon 2025

Acknowledgments

Cerebras for the lightning-fast AI API

Meta for the Llama 2 model
