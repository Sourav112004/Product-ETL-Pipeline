# System Architecture Report (Updated)

The following diagram illustrates the updated architecture of the AI assistant system, incorporating expanded backend processing and post-response management.

## Architectural Overview

```mermaid
graph TD;
    A[User Application] --> B[Backend API];
    B --> C[Authentication Service];
    C --> D[MySQL Database];
    D --> E[Users];
    D --> F[Profile Attributes];
    D --> G[Notebook Entries];
    G --> H[Python ETL Pipeline];
    H --> I[Extract];
    H --> J[Transform];
    H --> K[Load];
    K --> L[AI Context Builder];
    L --> M[Context JSON];
    M --> N[LLM API];
    N --> O[Response Processor - Python];
    O --> P[Save Goals];
    O --> Q[Update Notebook];
    O --> R[Store Chat];
    P --> D;
    Q --> D;
    R --> D;
```

## System Components

1.  **Application Layer**: Generic frontend supporting various interfaces.
2.  **Authentication & Data Layer**: Centralized API with MySQL for user and notebook data.
3.  **ETL & Context Layer**: Robust pipeline extracting notebook data to build structured context for AI.
4.  **Processing & Storage Layer**: LLM interaction followed by post-processing to update goals, notebooks, and chat history.
