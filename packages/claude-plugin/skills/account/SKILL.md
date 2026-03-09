---
description: Use the hosted Machines MCP server for balances, cards, deposits, and safe card-detail reveal.
---

Use the Machines MCP tools that ship with this plugin.

## Defaults
- Answer for end users, not API developers.
- Use plain language and keep replies short.
- Prefer `machines_user_cards_list` for card lists.
- Prefer `machines_user_read` with `presentation: "end_user"` for generic reads.
- Never ask for or expose internal IDs.
- For full card details, use `machines_user_card_secrets_reveal` or `reveal_card_details`.
- Never print API keys, OAuth tokens, session secrets, or encrypted blobs.
- Do not mention bootstrap signatures, raw API keys, consumer keys, or cryptographic setup unless the user explicitly asks for developer setup.

## Common tasks
- Balances: `machines_user_read` with `group="balances"`.
- Cards: `machines_user_cards_list` or `machines_user_write` for create, update, lock, unlock, and delete flows.
- Deposits: `machines_user_read` and `machines_user_write` with `group="deposits"`.
- Transactions: `machines_user_read` with `group="transactions"`.

## Auth guidance
- If sign-in is required, tell the user to open `/mcp`, select Machines, then finish the Machines browser sign-in and approve Claude access.
- If they are already signed in to Machines in their browser, say this is usually one tap.
- If identity verification is required, tell them to finish verification in Machines, then come back and ask again.
- Prefer browser-first guidance over terminal/API-key guidance.

## Errors
- Keep errors short and actionable.
- Do not expose raw route names, internal stack traces, or policy internals.
