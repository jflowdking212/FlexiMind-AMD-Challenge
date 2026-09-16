# Technology Stack

This document separates the **existing FlexiMind foundation** from **challenge-specific planned technology**.

## Existing Foundation

### Frontend
- React
- TypeScript
- Vite
- React Router
- Socket.IO client
- Recharts
- React Markdown

### Backend
- Node.js
- TypeScript
- Express
- Prisma
- Redis / ioredis
- BullMQ
- Socket.IO
- Zod
- Winston
- OpenAI SDK
- Pinecone client
- Docker-based development components

### Platform Capabilities
- task orchestration;
- agent/model routing;
- fallback behavior;
- cost controls;
- realtime task/status updates;
- API-based execution;
- persistence and caching.

## Challenge-Specific Planned Stack

| Component | Planned Technology | Status |
|---|---|---|
| AMD compute | Challenge-provided / approved AMD environment | Pending |
| GPU software stack | ROCm | Pending |
| Open-source inference model | To be selected after environment verification | Pending |
| AMD adapter | TypeScript service adapter | Pending |
| Metrics | Structured execution trace + benchmark CSV/JSON | Pending |
| Evaluation | Task-specific verifier + benchmark cases | Pending |

## Technology Disclosure Rule

A technology should be selected in the Lablab submission only when one of these is true:

1. it is already part of the actual project runtime; or
2. it has been integrated into the challenge branch/repository and can be demonstrated.

Development assistants or tools used only to write code should not automatically be listed as runtime technologies.
