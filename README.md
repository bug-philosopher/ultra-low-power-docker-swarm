# Ultra Low Power Docker Swarm
A high performance, energy efficient Docker Swarm cluster powered by ZimaBlade and ZimaBoard systems


                     ┌───────────────────────────────┐
                     │  Portainer Server (external)  │
                     │  - Manages Swarm remotely     │
                     │  - Deployed elsewhere on LAN  │
                     └─────────────┬─────────────────┘
                                   │
                         2.5 GbE LAN Backbone
                                   │
        ┌────────────────────────────────────────────────────┐
        │                      Swarm Cluster                 │
        │                                                    │
        │  ZimaBlade 8GB  → Manager (HELIOS)                 │
        │  ZimaBoard 8GB   → Worker (EOS-01)                 │
        │  ZimaBoard 8GB   → Worker (SELENE-02)              │
        │                                                    │
        │  DietPi + Docker + Portainer Agent on all nodes    │
        └────────────────────────────────────────────────────┘

## Software Stack

| Layer | Software | Purpose |
|:--|:--|:--|
| **Base OS** | [DietPi](https://dietpi.com/) | Lightweight Debian-based OS tuned for SBCs. |
| **Container Runtime** | [Docker CE](https://www.docker.com/) | Container engine across all nodes. |
| **Cluster Orchestration** | [Docker Swarm](https://docs.docker.com/engine/swarm/) | Native orchestration layer for container services. |
| **Management UI** | [Portainer CE](https://www.portainer.io/) | Web interface for deploying and monitoring containers and stacks. |
| **Additional Tools** | [Cockpit](https://cockpit-project.org/) | Simple system management and metrics dashboards. |
