# Ash Vibez

Agent-optimized documentation for building Elixir applications with the Ash Framework.

## What is this?

This repository provides structured guidance that AI agents can fetch and follow to create Ash Framework applications. It uses the `llms.txt` convention for agent discovery.

## Usage

### Option 1: Add to your AGENTS.md or CLAUDE.md

Add this to your project's `AGENTS.md` or `CLAUDE.md` file:

```markdown
## Ash Framework

When working with Ash Framework, fetch the guidance documentation:

1. Fetch the index: https://raw.githubusercontent.com/bradleygolden/ash_vibez/main/llms.txt
2. Follow links to relevant documentation based on the task
3. Use the patterns and commands from the fetched docs

For creating new Ash projects, reference the new-project guide.
For discovering available extensions, reference the extensions guide.
```

### Option 2: Direct instruction

Tell your agent:

> "Fetch https://raw.githubusercontent.com/bradleygolden/ash_vibez/main/llms.txt for Ash Framework guidance"

## For Agents

Fetch the index to discover available documentation:

```
https://raw.githubusercontent.com/bradleygolden/ash_vibez/main/llms.txt
```

## For Humans

If you're a developer, you can browse the `docs/` directory directly or visit [ash-hq.org](https://ash-hq.org) for the official Ash Framework documentation.

## Current Coverage

- **New Project Creation**: How to scaffold new Ash projects using the Ash HQ installer or Igniter CLI
- **Extensions**: Available Ash extensions and how to discover more dynamically
- **Usage Rules**: Install the `usage_rules` library to get package-author guidance for existing projects
