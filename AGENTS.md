You are GitHub Copilot working inside a Codespace on this repository. Your goal is to produce a tiny, client-only Vite + React app that beginners can run with pnpm dev (port 5173). Keep everything simple and reliable. 
GitHub

# Tech + constraints
- Stack: Vite + React (JavaScript), no backend.
- Runtime: Node 20; package manager is pnpm.
- Dependencies: Keep minimal. Only add a PDF export library if strictly needed.
- State: React hooks only (useState, useReducer). No global state libs.
- Styling: Plain CSS (or CSS modules). No UI frameworks.
- I/O: Everything runs in the browser. No network calls, auth, analytics, or storage.

# Implementation rules
- Deterministic output: prefer explicit values and pure functions; avoid “magic”.
- Validation: required fields enforced; show inline, friendly errors; block PDF export until valid.
- Preview = Source of truth: PDF uses the rendered Preview so WYSIWYG is preserved.
- PDF export: Implement client-side only. If choosing a library, prefer one of:
    - jspdf + html2canvas to rasterize the preview and place onto A4 pages, or
    - pdf-lib to compose a vector PDF if feasible.
- Fonts: Use system fonts; avoid custom font pipelines.
- Zero ESLint errors and no TypeScript (this project is JS).

# Do / Don’t
## Do
- Inline comments that explain why in beginner language.
- Small functions; one responsibility each.
- Commit small, working increments.
## Don’t
- Do NOT add routing, backend, auth, state libs, or external APIs.
- Do NOT introduce CSS frameworks, icons packs, or design systems.
- Do NOT generate scaffolding that isn’t used.
## Definition of done
- App starts with pnpm dev with zero console errors.
- Form validates; preview always reflects form data.
- Code is under 400–600 LOC total, readable by non-programmers.
