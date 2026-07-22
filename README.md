# Guardrails, MCP & Tools — Workshop Slides

A [Slidev](https://sli.dev) deck for the workshop **"Guardrails, MCP & Tools in Agentic Engineering"** — giving coding agents real capabilities and keeping them on the rails.

- **Theory (≈ 12 min):** tools as typed contracts, MCP architecture, threat model, layered guardrails, hooks — including a hook-event comparison across Claude Code, Codex CLI, OpenCode, and Pi.
- **Hands-on lab (≈ 60–75 min):** control first, then capability.
  1. **Hooks (≈ 30 min)** — one exercise, three verdicts: a `PreToolUse` hook that **denies** destructive commands and secret access, one that **asks** a human before anything irreversible, and a `PostToolUse` hook that **observes** into a JSONL audit trail. Ported to an OpenCode plugin and a Pi extension.
  2. **Ship a tool via MCP (≈ 20 min)** — a ticket-tracker server in Python, with TypeScript and Rust ports.
  3. **Compose (≈ 10 min)** — point the guardrails from step 1 at the tools from step 2 by editing a single matcher, then argue about defense in depth.
  4. **Bonus (≈ 10 min)** — red-team it, including the `@`-reference gap that walks straight past a `Read` hook.
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
