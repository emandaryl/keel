# Keel

> **"Turn your idea into a finished app — no coding required."**

**Keel** is a free developer-tooling product and AI-coding-agent scaffolding kit. It enables anyone—from non-technical founders and students to experienced creators—to turn a plain-English idea into a fully working application, website, or script using modern AI coding assistants, with zero initial setup, configuration, or technical overhead.

---

## 📖 Table of Contents
- [What is Keel?](#-what-is-keel)
- [How It Works](#-how-it-works)
- [Repository Structure](#-repository-structure)
- [Supported Assistants](#-supported-assistants)
- [Inside the Keel Kit](#-inside-the-keel-kit)
- [Getting Started](#-getting-started)
- [License](#-license)

---

## 🧭 What is Keel?

Keel solves a common problem: when you ask an AI coding assistant to build an app from scratch, it often guesses the architecture, makes suboptimal choices, asks you technical questions you might not know how to answer, and delivers a half-working product. 

Keel acts as a **pre-baked knowledge injection** for your assistant. By providing a strict structure, conventions, and pre-filled instructions, Keel guides your AI assistant to build your app using a proven, robust tech stack matching your idea, without you ever seeing a line of config or code.

---

## ⚡ How It Works

From a plain-language idea to a finished application in three steps:

```
[ Step 1: Idea ] ──> Describe what you want in plain words (e.g., "A daily water tracker").
       │
[ Step 2: Plan ] ──> The AI repeats the plan in plain English. No technical jargon. You approve or tweak.
       │
[ Step 3: App  ] ──> Keel builds, runs verification checks, and hands you the finished app link.
```

1. **Describe Your Idea:** Open the Keel workspace folder with your favorite AI assistant and describe your idea in everyday language.
2. **Confirm the Plan:** The assistant will draft an implementation plan in plain words. Once you say yes, it gets to work.
3. **Get Your App:** The assistant sets up the database, frontend, backend API, runs validation checks to ensure key features work, and gives you the local URL to access it.

---

## 📁 Repository Structure

This repository contains the marketing pages, documentation, and the packaged kit itself:

*   **[keel-landing.html](file:///Users/emandaryl/Developer/Personal/keel/keel-landing.html):** The interactive, highly polished landing page introducing Keel, its benefits, features, and pricing.
*   **[keel-quickstart.html](file:///Users/emandaryl/Developer/Personal/keel/keel-quickstart.html):** A step-by-step setup guide with a detailed walkthrough of a real conversation building a water-tracker application.
*   **[keel/](file:///Users/emandaryl/Developer/Personal/keel/keel):** The actual scaffolding template containing the empty skeleton, agent instructions, conventions, and rules.
*   **[KEEL_CONTEXT.md](file:///Users/emandaryl/Developer/Personal/keel/KEEL_CONTEXT.md):** The project context, guidelines, and handoff document (Note: This contains developer-oriented notes and legacy architecture guidelines).
*   **[.gitignore](file:///Users/emandaryl/Developer/Personal/keel/.gitignore):** System file configuration to exclude local metadata.

---

## 🤖 Supported Assistants

Keel is designed to work seamlessly with the AI coding tools you already use:
*   **Claude Code**
*   **Cursor**
*   **Antigravity**

---

## 📦 Inside the Keel Kit (`keel/`)

The `keel/` template directory contains the following layout:
*   `START-HERE.md` — The entrypoint guide for bootstrap prompts.
*   `QUICKSTART.md` — Step-by-step walkthrough of a worked conversation.
*   `AGENTS.md` — The single source of truth at the project root that guides the assistant (autonomously chooses Next.js/Supabase, HTML/CSS/JS, FastAPI, Python, or Flutter depending on your project type).
*   `CLAUDE.md`, `GEMINI.md`, `.cursor/`, `.github/` — Thin adapters pointing back to `AGENTS.md` to prevent instruction drift across different tools.
*   `docs/` — Standardized folder structure including `CONVENTIONS.md`, `ARCHITECTURE.md`, `PRD.md`, `SETUP.md`, `TESTING.md`, `DECISIONS.md`, and `USAGE.md` to keep the assistant's progress organized.

---

## 🚀 Getting Started

To explore the landing pages locally:
1. Open [keel-landing.html](file:///Users/emandaryl/Developer/Personal/keel/keel-landing.html) in your web browser.
2. Click **Quickstart** or open [keel-quickstart.html](file:///Users/emandaryl/Developer/Personal/keel/keel-quickstart.html) to see the step-by-step flow.

To build an app using Keel:
1. Copy the `keel/` directory to a new folder on your computer.
2. Open that folder with your AI coding assistant.
3. Follow the instructions in `START-HERE.md`.

---

## 📄 License

Keel is open-source and free to use for both personal and commercial projects.
