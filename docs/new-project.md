# Creating a New Ash Project

This guide covers how to create a new Ash Framework project from scratch.

## Quick Reference

For agents, use the Igniter method (non-interactive):

```bash
# Install required archives (one-time)
mix archive.install hex igniter_new

# Create Ash project
mix igniter.new my_app --install ash && cd my_app

# Or with Phoenix
mix archive.install hex phx_new
mix igniter.new my_app --install ash,ash_phoenix --with phx.new && cd my_app
```

## Method 1: Ash HQ Installer (Interactive)

The Ash HQ installer provides an interactive web-based setup with feature selection.

```bash
sh <(curl 'https://ash-hq.org/install/my_app') && cd my_app
```

Replace `my_app` with your desired application name.

### Available Presets

The installer prompts for:

- **Web Frameworks**: Phoenix, GraphQL (AshGraphql), JSON:API (AshJsonApi)
- **Data Layers**: PostgreSQL (AshPostgres), SQLite (AshSqlite)
- **Authentication**: Password, magic links, API keys, OAuth2 (AshAuthentication)
- **Additional Features**: Various extensions and tools

### When to Use

- Interactive development sessions
- Exploring available options
- First-time Ash users

## Method 2: Igniter CLI (Programmatic)

Igniter provides non-interactive project creation, ideal for agents and scripts.

### Prerequisites

Install the required Mix archives:

```bash
mix archive.install hex igniter_new
```

For Phoenix projects, also install:

```bash
mix archive.install hex phx_new
```

### Create a Plain Ash Project

```bash
mix igniter.new my_app --install ash
cd my_app
```

### Create an Ash + Phoenix Project

```bash
mix igniter.new my_app --install ash,ash_phoenix --with phx.new
cd my_app
```

### Common Extension Combinations

```bash
# Full-stack with Postgres
mix igniter.new my_app --install ash,ash_postgres,ash_phoenix --with phx.new

# With authentication
mix igniter.new my_app --install ash,ash_postgres,ash_phoenix,ash_authentication --with phx.new

# API-only with JSON:API
mix igniter.new my_app --install ash,ash_postgres,ash_json_api

# GraphQL API
mix igniter.new my_app --install ash,ash_postgres,ash_graphql
```

### Available Extensions

Common extensions:

| Extension | Package | Purpose |
|-----------|---------|---------|
| PostgreSQL | `ash_postgres` | PostgreSQL data layer |
| SQLite | `ash_sqlite` | SQLite data layer |
| Phoenix | `ash_phoenix` | Phoenix integration, forms |
| JSON:API | `ash_json_api` | REST API following JSON:API spec |
| GraphQL | `ash_graphql` | GraphQL API |
| Authentication | `ash_authentication` | User authentication |
| Background Jobs | `ash_oban` | Oban integration for async jobs |

For the complete list of extensions and how to discover more, see [Extensions](extensions.md).

## Next Steps

After creating your project:

Research the necessary [usage rules](https://raw.githubusercontent.com/bradleygolden/ash_vibez/refs/heads/main/docs/usage-rules.md)
