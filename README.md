# Guardrails, MCP & Tools — Workshop Slides

A [Slidev](https://sli.dev) deck for the workshop **"Guardrails, MCP & Tools in Agentic Engineering"** — giving coding agents real capabilities and keeping them on the rails. The hands-on lab is built on **OpenCode**.

- **Theory (≈ 12 min):** tools as typed contracts, MCP architecture, threat model, layered guardrails — including a guardrail comparison across OpenCode, Claude Code, Codex CLI, and Pi.
- **Hands-on lab (≈ 60–75 min), built on [OpenCode](https://opencode.ai):** control first, then capability.
  1. **Plugins (≈ 30 min)** — one TypeScript file in `.opencode/plugins/`, three powers: **deny** by throwing, **rewrite** the tool arguments so a dangerous call becomes a safe one, and **observe** into a JSONL audit trail. Plus the fourth verdict you *don't* write code for — the declarative `permission` config, which is where `ask` actually lives. The same policy, wired for Claude Code and Pi, is in an appendix at the end of the deck.
  2. **Build an MCP server (≈ 20 min)** — a ticket-tracker server in Python, registered from `opencode.json`, with TypeScript and Rust ports.
  3. **Guarding your own tools (≈ 10 min)** — gate your own MCP tools two different ways and argue about which one belongs in a pull request.
  4. **Bonus (≈ 10 min)** — red-team it: prompt injection through a tool result, the subagent path, and the rewrite the model can't see.
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
