# Guardrails, MCP & Tools — Workshop Slides

A [Slidev](https://sli.dev) deck for the workshop **"Guardrails, MCP & Tools in Agentic Engineering"** — giving coding agents real capabilities and keeping them on the rails.

- **Slides 1–12:** theory (≈ 12 min) — tools as typed contracts, MCP architecture, threat model, layered guardrails, hooks.
- **Slides 13–27:** the hands-on lab (≈ 60–75 min) — build a ticket-tracker MCP server, write a PreToolUse guardrail hook, add a human-approval gate + JSONL audit trail, then red-team your own setup.
- [`exercises.md`](./exercises.md) — the same lab as a self-contained handout for participants.

## Usage

```bash
npm install
npm run dev      # present at http://localhost:3030
npm run build    # static SPA in dist/
npm run export   # PDF export (installs playwright-chromium on first run)
```

Edit [`slides.md`](./slides.md) to change the deck — speaker notes (with per-slide timings) are in the HTML comments and show up in presenter mode (`p`).

Built on [Slidev](https://sli.dev) with the `seriph` theme.
