# AI Business Strategy Agent

## Project Overview

This project is a **Ghana AI Strategy & Automation Agent** — an intelligent system that identifies high-ROI AI opportunities for small and medium enterprises (SMEs) in **Greater Accra**. The core strategy is **"Operational Digitization"**: moving businesses from manual paper-based and WhatsApp-driven workflows to automated AI systems.

The agent analyzes business data, generates actionable recommendations, and integrates with real-world tools to streamline strategic planning — with a focus on sectors where automation delivers the fastest returns.

## Business Context (2026)

- **Target Market:** SMEs in Greater Accra, Ghana
- **Focus Sectors:**
  - **Hospitality** — Boutique hotels and guest houses
  - **Logistics** — Delivery and fleet coordination
  - **Private Schools** — Admissions, parent communication, and admin workflows
- **Value Proposition:** Support Ghana's **"24-Hour Economy"** push by deploying AI that handles night-shift inquiries, after-hours bookings, and round-the-clock customer engagement — so businesses never go offline.
- **Strategy:** Identify where manual/WhatsApp workflows create bottlenecks, then recommend or build AI-powered automations that save time and money.

## Tech Stack

- **Language:** Python 3.11+
- **Backend / Database:** Supabase (PostgreSQL, Auth, Edge Functions, Realtime) — handles data storage, user authentication, and real-time updates
- **AI / LLM:** Anthropic Claude API — powers the reasoning and recommendation engine
- **Hosting:** Render — for deploying the API and background workers
- **Framework:** FastAPI (for API endpoints)
- **Environment Management:** python-dotenv, virtualenv

## Coding Standards

### Python Style

- Follow **PEP 8** for all Python code.
- Use **type hints** on all function signatures.
- Keep functions short and single-purpose — one function, one job.
- Use `snake_case` for variables and functions, `PascalCase` for classes.
- Prefer f-strings for string formatting.

### Supabase Integration

- All database access goes through the **Supabase Python client** (`supabase-py`).
- Store connection credentials in environment variables (`SUPABASE_URL`, `SUPABASE_KEY`), never in code.
- Use Row Level Security (RLS) policies on all tables — no open access.
- Write database queries using the Supabase client's query builder, not raw SQL, unless complexity demands it.
- Keep Supabase client initialization in a single shared module (e.g., `src/db/client.py`).

### Documentation (CTE Educator Focus)

This project doubles as a **teaching resource** for Career & Technical Education (CTE) students. Every piece of code should be approachable for learners:

- **Docstrings on every public function and class.** Use the Google-style docstring format. Explain *what* the function does and *why* it exists, not just the parameters.
- **Inline comments for non-obvious logic.** If a student would ask "why?", add a short comment.
- **README and docs/ folder** should include plain-language explanations of architecture, setup, and key concepts (Supabase, API keys, environment variables, etc.).
- Avoid jargon without definition. When introducing a technical term for the first time, briefly explain it.

### Project Structure (Target Layout)

```
AI-Biz/
├── CLAUDE.md              # This file — project instructions for Claude
├── README.md              # Project overview and setup guide
├── requirements.txt       # Python dependencies
├── .env.example           # Template for environment variables
├── src/
│   ├── main.py            # Application entry point
│   ├── agent/             # AI agent logic and prompts
│   ├── db/                # Supabase client and database helpers
│   ├── models/            # Data models / schemas
│   └── utils/             # Shared utility functions
├── tests/                 # Unit and integration tests
└── docs/                  # Educational documentation and guides
```

### Testing

- Write tests using **pytest**.
- Aim for tests on all core agent logic and database interactions.
- Use fixtures for Supabase client mocking so tests run without a live database.

### Git Workflow

- Write clear, descriptive commit messages (imperative mood: "Add feature," not "Added feature").
- Keep commits focused — one logical change per commit.
- Use feature branches for new work.

### Environment & Secrets

- Never commit `.env` files, API keys, or credentials.
- Provide a `.env.example` with placeholder values so new contributors (or students) know what's needed.
- Required environment variables:
  - `SUPABASE_URL` — Your Supabase project URL
  - `SUPABASE_KEY` — Your Supabase anon/public key
  - `ANTHROPIC_API_KEY` — Claude API key for the AI agent

### Environment & Secrets (Render Deployment)

- `RENDER_API_KEY` — Render API key (for deployment automation, if used)
- Render environment variables should mirror the `.env.example` entries above.

## Key Principles

1. **Clarity over cleverness** — Write code a CTE student can read and learn from.
2. **Security by default** — RLS, env vars, input validation.
3. **Small, testable pieces** — Modular functions and classes that can be understood in isolation.
4. **Practical AI** — The agent should produce recommendations a real Ghanaian business owner can act on.
5. **24-Hour Economy ready** — Design for always-on operation: async processing, queue-based workflows, and graceful handling of off-hours requests.
