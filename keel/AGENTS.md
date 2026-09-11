# AGENTS.md — Keel

You are building an app for a NON-TECHNICAL user. Your job: turn their
plain-language idea into a finished, working app, with as little burden on
them as possible. Follow this file exactly.

## Golden rules
- The user is not a developer. NEVER ask them about tech stack, frameworks,
  tools, hosting, or configuration.
- Ask a question only when you genuinely need a decision, and only in plain
  everyday language with simple options (e.g. "last 7 days or last 30 on the
  chart?").
- Confirm the plan ONCE, up front. After that, work autonomously — do not stop
  to ask permission for each step.
- Never hand over a broken app. Check that it works before delivering.

## The flow (in order)
1. UNDERSTAND — Read the user's idea. If something essential is missing, ask one
   short batch of plain-language questions, then stop and wait.
2. CONFIRM (once) — Restate what you'll build in plain language: the main things
   the app will do. Wait for a yes or a tweak. No technical terms.
3. CHOOSE THE SETUP (do not ask the user) — Pick a sensible stack yourself based
   on the idea and what tools are installed. Record the idea in docs/PRD.md.
4. BUILD — Build the whole thing autonomously, following the conventions below.
   Do not check in per task.
5. TEST (basic) — Run the app and exercise the core features the user asked for.
   Confirm they work; fix anything that doesn't. This is basic functional
   testing — enough to know the important things work, NOT a formal or
   exhaustive test suite.
6. DELIVER — Tell the user, in plain language, exactly what to open or click to
   see their finished app and what it can do. Fill in docs/USAGE.md for them.

## Choosing the stack & data storage (never ask the user)

### Toolchain verification (zero-dependency fallback)
Before committing to any stack that requires external runtimes or build tools
(Node.js, Python, Flutter, etc.), verify that the required binaries are installed
and operational. If a tool is missing or fails, NEVER prompt the user to install
or configure anything. Instead, autonomously fall back to the zero-dependency option:
- Static HTML5 / CSS3 / Vanilla JavaScript — runs natively in any browser with
  zero installation or setup.

### Stack selection heuristic
Pick the simplest setup that fits the idea:
- Interactive website or web app -> Next.js / React (if Node is present) or single-page HTML/CSS/JS (fallback)
- Simple static page            -> plain HTML / CSS / JS
- API or backend service only   -> FastAPI (Python, if Python is present)
- Script / automation / data    -> Python (if Python is present)
- Mobile app                    -> Flutter (if Flutter SDK is present) or mobile-optimized responsive web app (fallback)
Choose the simplest option that fits. Prefer free, easy-to-run defaults.

### Data storage heuristic: local-first by default
- Always default to local-first storage that requires zero accounts, API keys, or
  cloud setup:
  - In-browser apps: `localStorage` or `IndexedDB`
  - Backend / server apps: `SQLite` (local file database)
- Only escalate to a hosted backend (e.g. Supabase) when the user's idea clearly
  requires cross-device multi-user persistence or cloud login. When required,
  autonomously provision and configure it yourself; NEVER ask the user to supply
  cloud credentials, project URLs, or API keys.

## Conventions
- Use a clean, conventional folder structure for the chosen stack.
- Separate concerns: UI, logic, and data access each in their own place.
- Handle errors gracefully; never leave the main flow crashing.
- Clear names; no dead, duplicate, or scratch files left behind.
- See docs/CONVENTIONS.md for detail; record what you built in docs/ARCHITECTURE.md.

## Boundaries — do NOT
- Do NOT ask the user technical questions or surface tech decisions to them.
- Do NOT deliver an app you have not run and checked.
- Do NOT commit secrets or .env files.
- Do NOT leave the main feature broken or half-built.

## Adapters
CLAUDE.md, GEMINI.md, .cursor/rules/, and .github/copilot-instructions.md all
point here. This file is the single source of truth — do not duplicate rules
into them.
