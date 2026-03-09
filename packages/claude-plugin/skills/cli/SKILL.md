---
description: Use the local Machines CLI for setup, login, KYC browser handoff, or when the user explicitly wants terminal commands.
---

Use the local Machines CLI when the Machines MCP plugin is not connected yet, the user asks for CLI or terminal help, or a browser handoff is required.

## Command selection
- Prefer the installed `machines` command.
- If `machines` is unavailable, fall back to `npx machines-cash@latest ...`.
- Use `--json` when structured output is useful.
- Do not invent shell commands or alternate package names.

## Common setup flows
- Login: `machines login`
- Browser KYC: `machines user create --browser`
- KYC status: `machines kyc status`
- Manual Claude fallback: `machines mcp install --host claude`
- MCP OAuth login: `machines mcp auth login`
- Health check: `machines mcp doctor`

## Operational flows
- Balance: `machines balance`
- Deposit assets: `machines deposit assets`
- Create card: `machines card create --name "<name>" --limit <usd> --frequency per30DayPeriod`
- List cards: `machines card list --json`
- Reveal card: `machines card reveal --last4 <last4> --json`

## Safety
- Prefer browser-based login for humans and `machines login --agent` only when the user clearly needs CLI-only auth.
- Reveal full card details only when the user explicitly asks.
