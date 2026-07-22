# Guardrails, MCP & Tools — Workshop Slides

A [Slidev](https://sli.dev) deck for the workshop **"Guardrails, MCP & Tools in Agentic Engineering"** — giving coding agents real capabilities and keeping them on the rails. The hands-on lab is built on **OpenCode**.

- **Theory:** tools as typed contracts, MCP, the threat model, guardrail layers, sandboxing, and review — with a guardrail comparison across OpenCode, Claude Code, Codex CLI, and Pi.
- **Lab, built on [OpenCode](https://opencode.ai):** Part 1 — plugins. One TypeScript file in `.opencode/plugins/`: **deny** by throwing, **rewrite** the tool arguments, **observe** into a JSONL audit trail, plus the declarative `permission` config where `ask` lives.
- **Appendix:** the same guard as a Claude Code hook and a Pi extension, then the full MCP lab — build a ticket server (Python, TypeScript, Rust), gate your own tools two ways, and red-team the setup.
- [`exercises.md`](./exercises.md) — the same lab as a self-contained handout for participants.

## Usage

```bash
npm install
npm run dev      # serve at http://localhost:3030
npm run build    # static SPA in dist/
npm run export   # PDF export (installs playwright-chromium on first run)
```

Edit [`slides.md`](./slides.md) to change the deck — speaker notes are in the HTML comments and show up in speaker view (`p`).

Built on [Slidev](https://sli.dev) with the `seriph` theme.
