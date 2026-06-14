# PrepNiti

An anonymous community and mock test preparation platform designed for competitive exam aspirants. PrepNiti bridges the gap between collaborative community discussions and structured practice workspaces.

---

## Architecture & Services

The platform is designed as a microservices architecture to segregate concerns between candidate-facing features, internal admin controls, and AI-driven document processing.

*   **`prepniti-backend`**: Core REST API built in Go (Gin, GORM). It manages the database schemas (PostgreSQL) for users, community posts, tasks, and test attempt records. Implements JWT-based secure auth and routes for candidate portals.
*   **`prepniti-admin-api`**: Separate administrative Go backend designed to handle privileged operations including mock compilations, metadata edits, and administrative audit logging.
*   **`prepniti-question-extractor`**: A FastAPI-based Python service. It handles PDF uploads of competitive exam papers and uses Google's Gemini API to parse structure, options, explanations, and key metadata into formatted JSON data for mock test ingestion.
*   **`prepniti-web`**: The candidate-facing Next.js frontend, styled with Tailwind CSS, utilizing React Query for state management and ApexCharts/Recharts for performance visualization.
*   **`prepniti-admin`**: Next.js-based administrator console featuring drag-and-drop question builders, audit logs inspection, and mock test publishing pipelines.

---

## Core Features

### 1. Interactive Mock Test Workspace
*   **Exam Simulation**: A custom client interface simulating actual computer-based test conditions.
*   **Security Monitoring**: Built-in hook to detect tab-switching or focus loss, enforcing exam integrity with warning dialogs.
*   **Performance Evaluation**: Auto-evaluates answer submissions, calculating percentages, tracking timing logs, and rendering detailed explanations.

### 2. PrepCoach Performance Insights
*   **Study Time Logging**: Visual tracker with category metrics and interactive heatmaps.
*   **Mock Test Trends**: Visual graphs (Recharts) mapping percentage scores over successive mock attempts.
*   **Personalized Recommendations**: Context-aware engine that analyzes historical mock data and logs to suggest immediate actions (e.g., "Resume Mock Tests" or "Focus on Accuracy").

### 3. Anonymous Discussion Forums
*   A Reddit-style community interface allowing aspirants to share interview experiences, mock results, and preparation strategies anonymously.

### 4. Admin Control Center & Ledger
*   **AI-Assisted Ingestion**: Upload mock test PDFs and automatically compile them into clean database schemas.
*   **Immutable Operations Audit**: A secure log capturing administrative transactions (IP address, administrator user, specific actions, timestamps). Features interactive tables powered by TanStack Table for sorting and paginating logs.

---

## Technology Stack

*   **Backend Services**: Go (Gin, GORM), Python (FastAPI)
*   **Frontend Interfaces**: TypeScript, Next.js (App Router), Tailwind CSS, TanStack Table (v8)
*   **Database**: PostgreSQL, Supabase
*   **Orchestration & DevOps**: Docker, Docker Compose, Multi-stage alpine builds

---

### Author & Maintainer
*   **Jayant Verma** ([@jayantverma](https://github.com/jayantverma)) — [jayantverma8533@gmail.com](mailto:jayantverma8533@gmail.com)