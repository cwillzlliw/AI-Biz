# AI Business Strategy Agent

## Project Overview

This project is an **AI Business Strategy Agent** — an intelligent system that helps small businesses and entrepreneurs make data-driven decisions about marketing, operations, pricing, and growth. It analyzes business data, generates actionable recommendations, and integrates with real-world tools to streamline strategic planning.

## Tech Stack

- **Language:** Python 3.11+
- **Backend / Database:** Supabase (PostgreSQL, Auth, Edge Functions, Realtime)
- **AI / LLM:** Anthropic Claude API
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

## Key Principles

1. **Clarity over cleverness** — Write code a CTE student can read and learn from.
2. **Security by default** — RLS, env vars, input validation.
3. **Small, testable pieces** — Modular functions and classes that can be understood in isolation.
4. **Practical AI** — The agent should produce recommendations a real business owner can act on.
