# ☁️ Global Restoration Telemetry & Cloud Architecture

This document describes the integration between the **Reconnection** client and **Google Cloud Platform** to manage global environmental recovery metrics and AI-driven mission generation.

```mermaid
graph TD
    subgraph Client_Side [Reconnection Client - Godot 4]
        A[Game Engine C#] --> B[API Client Manager]
    end

    subgraph GCP_Cloud_Infrastructure [Google Cloud Platform]
        B -->|HTTPS/JSON| C[Cloud Run: REST API]
        C --> D{Identity & Access}
        D -->|Authenticated| E[Firestore: NoSQL Database]
        E --> F[Cloud Functions: Metrics Aggregator]
        F --> G[Global Restoration Dashboard]
    end

    subgraph External_Services [Intelligence Layer]
        C --> H[Vertex AI: Dynamic Narrative]
    end

    %% Styling
    style GCP_Cloud_Infrastructure fill:#f1f8ff,stroke:#4285f4,stroke-width:2px
    style Client_Side fill:#fdf1f1,stroke:#e74c3c,stroke-width:2px
```