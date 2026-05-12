
<br/>
<div align="center">
<a href="https://github.com/ShaanCoding/ReadME-Generator">
<img src="https://raw.githubusercontent.com/daviddprtma/flowforge-ai/refs/heads/main/frontend/public/logo.png?token=GHSAT0AAAAAADXQ2JK6EUG2CJRXIJFGHBHA2QCTHOA" alt="Logo" width="80" height="80">
</a>
<h3 align="center">FlowForge AI</h3>
<p align="center">
An AI-powered workflow automation platform built with Node.js, Fastify, and various AI services.

<br/>
<br/>
<a href="https://www.youtube.com/watch?v=O5UkrptTa2o">View Demo Video FlowForge AI</a>  


</p>
</div>

## About The Project

✨ FlowForge AI: Where Intelligence Meets Automation
In the modern labyrinth of digital tasks and disjointed services, FlowForge AI emerges as the master architect of efficiency. It is not just another automation tool; it is an AI-powered orchestration engine designed to breathe life into your workflows.

Built on a robust foundation of Node.js and the high-performance Fastify web framework, FlowForge AI acts as the central nervous system for your automated processes. It seamlessly integrates with cutting-edge AI services, transforming static, rule-based automation into dynamic, intelligent agents capable of decision-making and adaptation.

🔮 The Vision
Imagine a platform where your workflows don't just execute—they think. FlowForge AI empowers you to design intricate, agent-based sequences where large language models (LLMs) act as the cognitive core. Whether it's intelligently routing data, generating contextual responses, or adapting to real-time inputs, this platform bridges the gap between simple automation and true AI-driven logic.

⚙️ Under the Hood
🧠 Intelligent Agent Core: Move beyond "if-this-then-that." Build workflows that leverage LLMs for nuanced understanding and action.

🐳 Container-Ready Architecture: With a provided Dockerfile and docker-compose.yml, deployment is as smooth as it is scalable—from local development to production environments.

🌐 Full-Stack Harmony: A complete ecosystem with a dedicated frontend and a TypeScript-first backend ensures type safety, maintainability, and a developer-friendly experience.

🔧 Modern Tech Stack: Crafted with meticulous attention using TypeScript (99.6% of the codebase), Fastify for speed, and a modular structure that welcomes extension.

🚀 A Glimpse of the Future
Though early in its journey (with its first commit on May 11, 2026), FlowForge AI represents a bold step toward a new class of AI-automation workflows. It invites developers and innovators to forge connections that were previously impossible, turning complex chains of tasks into a single, intelligent, and elegant flow.
### Built With

- [Typescript](https://www.typescriptlang.org/)
- [React](https://react.dev/blog/2022/03/29/react-v18)
- [Fastify](https://fastify.dev/)
- [MongoDB](https://www.mongodb.com/)
- [Redis](https://redis.io/)
- [Docker](https://www.docker.com/)
### Prerequisites

Read this section about how to get start with this FlowForge AI 

- Node.js v20 or later
- MongoDB v7 (local or cloud, e.g. MongoDB Atlas)
- Redis v7 (local or cloud, e.g. Upstash)
- API keys for any LLM providers you want to use

### Installation

1. Clone the repository
   ```sh
   git clone https://github.com/daviddprtma/flowforge-ai
   ```
2. Configure environment variables
   ```sh
   cp .env.example .env
   ```
3. Install dependencies
   ```sh
   # Backend
   npm install
   ```

   ```sh
   # Frontend
   cd frontend && npm install && cd ..
   ```
4. Run in development mode
   ```sh
   # Terminal 1 — backend API (hot-reload)
   npm run dev
   ```

   ```sh
   # Terminal 2 — frontend dev server
   cd frontend && npm run dev
   ```

Open http://localhost:5173 in your browser.

5. Production build
   ```sh
   # Build frontend into dist/public, then start the backend which serves it
   cd frontend && npm run build && cd ..
   npm run build
   npm start
   ```

## 🔑 Environment Variables

Copy `.env.example` to `.env` and fill in the values below.

### Core

| Variable | Description |
|----------|-------------|
| `PORT` | Port the backend listens on (default `3000`) |
| `MONGODB_URI` | MongoDB connection string |
| `REDIS_URL` | Redis connection string (default `redis://localhost:6379`) |
| `CORS_ORIGIN` | Frontend origin allowed by CORS (default `http://localhost:5173`) |

### LLM Providers

| Variable | Description |
|----------|-------------|
| `OPENAI_API_KEY` | OpenAI API key |
| `ANTHROPIC_API_KEY` | Anthropic API key |
| `GOOGLE_API_KEY` | Google Gemini API key |

### Google Workspace OAuth

| Variable | Description |
|----------|-------------|
| `GOOGLE_CLIENT_ID` | OAuth 2.0 client ID from Google Cloud Console |
| `GOOGLE_CLIENT_SECRET` | OAuth 2.0 client secret |
| `GOOGLE_REDIRECT_URI` | Redirect URI (e.g. `http://localhost:3000/api/oauth/google/callback`) |

### Slack OAuth

| Variable | Description |
|----------|-------------|
| `SLACK_CLIENT_ID` | Slack app client ID |
| `SLACK_CLIENT_SECRET` | Slack app client secret |
| `SLACK_REDIRECT_URI` | Redirect URI (e.g. `http://localhost:3000/api/oauth/slack/callback`) |

### Basecamp OAuth

| Variable | Description |
|----------|-------------|
| `BASECAMP_CLIENT_ID` | Basecamp app client ID |
| `BASECAMP_CLIENT_SECRET` | Basecamp app client secret |
| `BASECAMP_REDIRECT_URI` | Redirect URI |

---

## 🐳 Docker

The easiest way to run the full stack locally is with Docker Compose — it spins up the app, MongoDB, and Redis together.

```bash
# Copy and fill in your environment variables
cp .env.example .env

# Build and start all services
docker compose up --build
```

The app will be available at [http://localhost:3000](http://localhost:3000).

```bash
# Stop all services
docker compose down

# Stop and remove all data volumes
docker compose down -v
```

> **Deploying to Railway?**  
> Set all environment variables in your Railway project's Variables panel. MongoDB and Redis can be provisioned as Railway plugins or pointed at external services like Atlas and Upstash.

---

## 📁 Project Structure

```
flux/
├── src/                        # Backend (Node.js / Fastify)
│   ├── db/                     # Database connection & seed data
│   ├── engine/                 # Workflow execution engine
│   ├── llm/                    # LLM providers (OpenAI, Anthropic, Gemini)
│   │   └── providers/
│   ├── nodes/                  # Node executor implementations
│   ├── queue/                  # BullMQ job queue setup
│   ├── repositories/           # MongoDB data access layer
│   ├── routes/                 # Fastify API routes
│   ├── scheduler/              # Cron & polling trigger scheduler
│   ├── services/               # OAuth & credential services
│   ├── types/                  # Shared TypeScript types
│   ├── validation/             # Zod schemas
│   └── index.ts                # App entry point
│
├── frontend/                   # Frontend (React / Vite)
│   ├── public/
│   │   ├── logo.png            # Flux app logo
│   │   └── logos/              # Integration brand logos
│   └── src/
│       ├── api/                # API client functions
│       ├── components/
│       │   ├── canvas/         # React Flow canvas & node picker
│       │   ├── nodes/          # Node widgets & icons
│       │   ├── panels/         # Config panel & execution log panel
│       │   └── ui/             # Shared UI components
│       ├── hooks/              # React Query hooks (workflows, credentials, etc.)
│       ├── store/              # Zustand global state
│       └── types/              # Frontend TypeScript types
│
├── docker-compose.yml
├── Dockerfile
├── .env.example
└── package.json
```


## License

Distributed under the MIT License. See [MIT License](https://github.com/daviddprtma/flowforge-ai/blob/main/LICENSE) for more information.

## Video Demo Presentation📽️
Here's the demo video for FlowForge AI👇
<br> 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/O5UkrptTa2o/0.jpg)](https://www.youtube.com/watch?v=O5UkrptTa2o)

