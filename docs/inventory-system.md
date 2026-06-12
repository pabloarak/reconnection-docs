# 📦 Inventory & Classification System Architecture

This document outlines the technical flow for waste collection and processing within **Reconnection**, ensuring a decoupled architecture between the player actions and the world state.

```mermaid
graph TD
    A[Player Collects Waste] --> B{Inventory Full?}
    
    B -- No --> C[Store in Backpack]
    B -- Yes --> D[Max Capacity Warning]
    
    C --> E[Sorting Station]
    
    subgraph "Material Categorization"
        E --> F1[Textiles]
        E --> F2[Plastics]
        E --> F3[Metals]
        E --> F4[Glass]
        E --> F5[E-Waste]
    end
    
    %% Processing logic
    F1 --> G[Fiber Recovery]
    F2 --> H[Polymer Shredding]
    F3 --> I[Smelting Prep]
    F4 --> J[Glass Crushing]
    F5 --> K[Hazardous Components Removal]
    
    %% Outcomes
    G & H & I & J & K --> L[Storage Bins for Truck Pickup]
    L --> M[Sync: Global Restoration Metrics]+
```