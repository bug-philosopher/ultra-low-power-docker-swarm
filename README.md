# ultra-low-power-docker-swarm
A high performance, energy efficient Docker Swarm cluster powered by ZimaBlade and ZimaBoard systems


                     ┌───────────────────────────────┐
                     │  Portainer Server (external)   │
                     │  - Manages Swarm remotely      │
                     │  - Deployed elsewhere on LAN   │
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
