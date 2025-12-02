# Usage Rules Library

The `usage_rules` library is a dev tool that gathers LLM guidance directly from Ash package authors.

## What It Does

`usage_rules` collects `usage-rules.md` files from your dependencies and consolidates them into your project's `AGENTS.md` or `CLAUDE.md` file. Many Ash ecosystem packages include these files with guidance written by package authors.

## Accessing Usage Rules Without Installation

If you don't want to install the `usage_rules` package, you can access usage rules directly:

### From GitHub (Raw URLs)

Fetch usage rules directly from package repositories:

```
https://raw.githubusercontent.com/<org>/<package>/main/usage-rules.md
```

Examples:
- `https://raw.githubusercontent.com/ash-project/ash/main/usage-rules.md`
- `https://raw.githubusercontent.com/ash-project/ash_postgres/main/usage-rules.md`

### From the deps/ Folder

If dependencies are already installed, read the files directly:

```
deps/<package>/usage-rules.md
deps/<package>/usage-rules/<topic>.md
```

Examples:
- `deps/ash/usage-rules.md`
- `deps/ash_phoenix/usage-rules.md`
- `deps/ash/usage-rules/html.md`

## When to Use the Library Instead

Install `usage_rules` when:

- Working with an **existing Ash project** that needs agent guidance
- You want **up-to-date guidance** that stays in sync with your dependencies
- You need to **search hexdocs** efficiently from the command line
- You want **automatic consolidation** into a single file

## Benefits of the Library

- **Author-written guidance**: Rules come directly from package maintainers
- **Stays current**: Re-sync when you update dependencies
- **Reduces hallucinations**: Agents get accurate, package-specific patterns
- **Searchable docs**: Quick access to hexdocs from command line

## Documentation

For installation and usage instructions, see the official documentation:

https://hexdocs.pm/usage_rules/readme.html
