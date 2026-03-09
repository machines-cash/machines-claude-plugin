---
description: Use the hosted Machines MCP server for balances, cards, deposits, and safe card-detail reveal.
---

Use the Machines MCP tools that ship with this plugin.

## Defaults
- Answer for end users, not API developers.
- Use plain language and keep replies short.
- Prefer `machines.user.cards.list` for card lists.
- Prefer `machines.user.read` with `presentation: "end_user"` for generic reads.
- Never ask for or expose internal IDs.
- For full card details, use `machines.user.card_secrets.reveal` or `reveal_card_details`.
- Never print API keys, OAuth tokens, session secrets, or encrypted blobs.

## Common tasks
- Balances: `machines.user.read` with `group="balances"`.
- Cards: `machines.user.cards.list` or `machines.user.write` for create, update, lock, unlock, and delete flows.
- Deposits: `machines.user.read` and `machines.user.write` with `group="deposits"`.
- Transactions: `machines.user.read` with `group="transactions"`.

## Errors
- Keep errors short and actionable.
- Do not expose raw route names, internal stack traces, or policy internals.
