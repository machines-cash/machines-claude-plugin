# Claude Plugin Marketplace Release

This document is the maintainer runbook for the Machines Claude plugin and its marketplace harness.

## Artifact Layout

- Plugin source lives in `packages/claude-plugin/`.
- Marketplace harness lives at `.claude-plugin/marketplace.json` in the repo root.
- Public marketplace mirror lives at `https://github.com/machines-cash/machines-claude-plugin` and preserves the same layout.

Why: Claude URL-based marketplaces only fetch `marketplace.json`. Our plugin uses relative paths, so the supported install shape is a git-based marketplace or a direct plugin submission built from the mirrored public repo.

## Versioning

- Treat `packages/claude-plugin/.claude-plugin/plugin.json` as the release version source of truth.
- Bump the plugin version before any marketplace or Anthropic submission update.
- Use semantic versioning:
  - major for breaking behavior or renamed plugin components
  - minor for new Claude-facing features
  - patch for fixes and copy-only improvements

## Validation

Run these checks before submission:

```bash
cd /Users/ardaerturk/Documents/GitHub/machines-claude-plugin
claude plugin validate ./packages/claude-plugin
claude plugin validate .
```

From the repo root, confirm the marketplace harness works:

```text
/plugin marketplace add <git-url-or-local-path-to-this-repo>
/plugin install machines@machines-plugins
```

## Submission

1. Confirm plugin metadata, docs links, and repository URLs are current.
2. Verify the plugin MCP endpoint is `https://mcp.machines.cash/mcp?host=claude`.
3. Submit through Claude:
   - `https://claude.ai/settings/plugins/submit`
   - `https://platform.claude.com/plugins/submit`
4. Sync the public mirror from the monorepo source before submission. Keep `.claude-plugin/marketplace.json` and `packages/claude-plugin` layout identical between repos.

## Docs Sync

When the listing status changes:

- Update `https://docs.machines.cash/claude-plugin`.
- Update `docs/consumer/mcp-server.md` and `packages/cli/README.md` in the monorepo.
- Remove any temporary "if the listing is not visible yet" caveat after approval.
