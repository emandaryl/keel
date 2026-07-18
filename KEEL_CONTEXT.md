# KEEL — Project Context & Handoff

> Handoff document for Claude Code. Compiled 2026-07-15 from planning sessions in claude.ai.
> Read this fully before doing any work on the project.

---

## 1. What Keel Is

**Keel** (working name — a placeholder; name/domain/trademark availability still needs to be verified before committing) is a **dev-tooling product**: an AI-coding-agent scaffolding kit for the **Next.js 14 + FastAPI + Supabase** stack.

**Positioning / chosen landing-page headline:**
> "Your AI coding agent isn't the problem. Your repo never told it the rules."

**Why this project:** It was selected as the IP-safe side-hustle direction after fitness-domain ideas were ruled out due to the Metron employment IP-assignment agreement. It plays to a documented strength: AGENTS.md / SKILL.md / LLM-ready documentation conventions.

---

## 2. The Two Sides (do not conflate)

### Side A — INTERNAL (build this first; largely done)
A reusable, **empty** cross-tool docs skeleton + a **bootstrap/interview "first prompt"** for personal use:
- Drop the empty skeleton into a project folder
- Run the bootstrap prompt
- The agent learns the project (by reading an existing codebase, or by interviewing for stack, commands, conventions) and **populates** AGENTS.md + the docs set, then builds

### Side B — PRODUCT (finalize AFTER Side A)
**Keel, the packaged kit that is sold.** It is a **pre-filled instance** of the skeleton:
- AGENTS.md, CONVENTIONS.md, and all technical content are filled in **once** for the Next.js 14 + FastAPI + Supabase stack — that pre-filled knowledge IS the product
- Ships with a beginner **product prompt** (distinct from the internal bootstrap prompt)
- The buyer populates **nothing**

### The two different "first prompts"
| Prompt | Audience | Asks for |
|---|---|---|
| **Interview/bootstrap prompt** | Eman (internal, empty skeleton) | Stack, commands, conventions — defines the project once |
| **Product prompt** | Keel buyer | ONLY a plain-language idea. Nothing technical. |

---

## 3. Key Product Principle (non-negotiable)

The buyer experience must be **simple enough for a first-year IT student**:
- User provides ONLY (1) an agentic coding tool and (2) a plain-language idea
- User NEVER supplies tech stack, commands, conventions, or config
- All technical aspects are pre-baked into the kit; the agent does the rest

---

## 4. The Skeleton (built)

Structure of the reusable cross-tool docs skeleton:
- **AGENTS.md** at project root — single source of truth and entry point
- **Thin adapters** at tool-required locations, each containing only a pointer back to AGENTS.md (prevents drift):
  - `CLAUDE.md`
  - `GEMINI.md`
  - `.cursor/` rules
  - `.github/` (Copilot instructions)
- Full **docs/** set
- An example **SKILL.md**

---

## 5. Related but SEPARATE project — do not merge

There is a **stack-agnostic docs-generation SKILL** in planning (Jul 2026) — a skill that auto-generates the full agent docs set for any project (both existing codebases and greenfield). It was explicitly decided this is **separate from Keel**, keeping Keel free to stay opinionated about its one stack.

That separate skill's agreed standard (useful reference, since it evolved from the same thinking):
- AGENTS.md at root as single source of truth; thin adapters (CLAUDE.md, GEMINI.md, `.cursor/rules/project.mdc`, `.github/copilot-instructions.md`)
- All substantive agent-facing content under a namespaced `.agent/` folder:
  - `.agent/docs/` — ARCHITECTURE.md, CONVENTIONS.md, SETUP.md, TESTING.md, DECISIONS.md
  - `.agent/features/` — INDEX.md + per-feature folders (FEATURE.md, TASKS.md, optional `references/`)
  - `.agent/skills/` — INDEX.md + per-skill folders (SKILL.md, optional `references/`, optional `scripts/`)
- For Claude Code: pointer skills in `.claude/skills/` referencing canonical content in `.agent/skills/`
- Three output profiles: minimal / standard / full
- If Keel's internal skeleton is ever updated, consider whether to align with this `.agent/` layout — but that is a decision to make explicitly, not silently

---

## 6. Plan / Remaining Work

1. **Finalize Side B (the product):** pre-fill AGENTS.md + CONVENTIONS.md and the full docs set for Next.js 14 + FastAPI + Supabase
2. **Write/finalize the two first-prompt variants** (interview prompt for internal use; beginner product prompt for buyers)
3. **Landing page** — headline chosen (see above); page itself to be built
4. **Naming:** verify "Keel" (or pick alternative) — domain + trademark check, done manually by Eman before committing

---

## 7. Established Working Conventions (from other projects; apply here)

- Claude Code in terminal is the preferred tool; session-restart pattern: `/clear` then "Read AGENTS.md. [one sentence about current task]"
- One agent task at a time; agent reads AGENTS.md (and TASKS.md if present) before every task; mark sub-tasks complete as it goes; stop for human review before proceeding

---

## 8. Source Conversations (claude.ai)

- Main Keel planning: https://claude.ai/chat/20612325-3b85-41ac-b23f-76c3298a6926 ("Side hustle ideas for software developers", Jun 2026) — contains the original skeleton discussion, the two-sides clarification, and the landing-page/headline work
- Separate docs-skill planning: https://claude.ai/chat/06ee2c7a-4d15-4030-9f1d-fc5cc72cbcbc ("Auto-generating documentation for AI coding assistants", Jul 2026)

**Note:** The verbatim contents of the skeleton files, the drafted first prompts, and the landing-page copy beyond the headline live in the main planning conversation above — this document captures the decisions and structure, not every artifact word-for-word. If Claude Code needs the exact drafted text, retrieve it from that chat or from local files if already saved.
