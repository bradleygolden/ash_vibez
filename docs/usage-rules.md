# Usage Rules Library

The `usage_rules` library is a dev tool that gathers LLM guidance directly from Ash package authors.

## What It Does

`usage_rules` collects `usage-rules.md` files from your dependencies and consolidates them into your project's `AGENTS.md` or `CLAUDE.md` file. Many Ash ecosystem packages include these files with guidance written by package authors.

## When to Use It

Install `usage_rules` when:

- Working with an **existing Ash project** that needs agent guidance
- You want **up-to-date guidance** that stays in sync with your dependencies
- You need to **search hexdocs** efficiently from the command line

## Benefits

- **Author-written guidance**: Rules come directly from package maintainers
- **Stays current**: Re-sync when you update dependencies
- **Reduces hallucinations**: Agents get accurate, package-specific patterns
- **Searchable docs**: Quick access to hexdocs from command line

## Documentation

For installation and usage instructions, see the official documentation:

https://hexdocs.pm/usage_rules
