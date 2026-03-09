# Machines Claude Plugin

Official public mirror for the Machines Claude plugin and its marketplace harness.

## Layout

- Plugin source lives in `packages/claude-plugin/`.
- Marketplace harness lives in `.claude-plugin/marketplace.json`.
- The layout matches the internal monorepo so relative plugin paths stay valid.

## Install

In Claude Code:

```text
/plugin marketplace add https://github.com/machines-cash/machines-claude-plugin
/plugin install machines@machines-plugins
```

You can also validate locally:

```bash
claude plugin validate .
claude plugin validate ./packages/claude-plugin
```

## Structure

```text
.
├─ .claude-plugin/
│  └─ marketplace.json
├─ docs/
│  └─ claude-plugin-marketplace.md
└─ packages/
   └─ claude-plugin/
      ├─ .claude-plugin/
      │  └─ plugin.json
      ├─ .mcp.json
      └─ skills/
         ├─ account/SKILL.md
         └─ cli/SKILL.md
```

## Source Of Truth

The internal Machines monorepo remains the authoring source. This repository is the public marketplace-facing mirror.
