# Conventions

> Concrete conventions guiding the assistant when building apps in Keel. These apply across any stack the agent selects.

## Naming
- **Files and folders:** Use lowercase kebab-case (e.g., `water-log.js`, `habit-card.css`, `data-store.py`).
- **Functions and variables:** Use self-explanatory names matching language idioms (`camelCase` in JavaScript, `snake_case` in Python).
- **User-facing terms:** Use everyday language (e.g., `addWaterEntry`, `viewHistory`) rather than engineering abstractions.

## File & folder organization
- **Keep root clean:** Only root configuration, docs, and the primary entrypoint belong at the top level.
- **Separate concerns:**
  - UI and views in their own folder or file (e.g., `src/`, `components/`, or `index.html`)
  - Storage and data logic isolated from the presentation layer
  - Static media (icons, images) in an `assets/` or `public/` directory
- **No clutter:** Remove temporary scratch scripts, leftover test fixtures, and duplicate files before handing over the app.

## Code style / formatting
- Write clean, readable code with short comments explaining key logic.
- Favor simplicity over cleverness; avoid compressed one-liners.
- Keep dependencies minimal — use standard libraries and native browser features wherever practical.

## Patterns to follow
- **Local-first persistence:** Save data immediately (to `localStorage`, `IndexedDB`, or local `SQLite`) so user progress survives a refresh or restart without cloud setup.
- **Friendly empty states:** Show a helpful message when the app first opens with no data (e.g., "No entries yet — tap below to add your first glass of water!").
- **Responsive design:** Build mobile-friendly layouts that adapt gracefully to both phones and desktop screens.
- **Graceful degradation:** Catch errors defensively and show plain-language feedback rather than blank screens or console panics.

## Anti-patterns to avoid
- **No external accounts or credentials:** Never block the core app flow behind a third-party cloud signup or API key for v1.
- **No fragile dependency bloat:** Do not pull in heavy frameworks or plugins when standard HTML/CSS/JS or standard library modules do the job.
- **No console crashes:** Never deliver an app with unhandled promise rejections or unstyled error boundaries.
- **No exposed secrets:** Never write tokens or secrets into source files or commit `.env`.

## Testing conventions
- **Core flow verification:** Exercise the primary feature end-to-end (create, view, and update data) before reporting completion.
- **Persistence check:** Verify that adding data, closing/refreshing the page, and reopening it preserves the user's data.
- **Clean execution:** Ensure the dev server or application starts without runtime errors or missing import warnings.

## Commit & branch conventions
- Use clear, descriptive commit messages: `feat: add daily logging form`, `fix: resolve chart display on mobile`.
- For single-user projects, develop directly on `main`.
