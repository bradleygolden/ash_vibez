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

## Post-Setup Verification

After creating the project, verify the setup:

```bash
# Fetch dependencies
mix deps.get

# Compile (should complete without errors)
mix compile

# Start interactive console
iex -S mix
```

### For Projects with Postgres

```bash
# Create database
mix ash.setup

# Or manually
mix ecto.create
mix ash.migrate
```

### Test Basic Operations

In `iex -S mix`, you can verify Ash is working:

```elixir
# List configured domains
Application.get_env(:my_app, :ash_domains)
```

## Project Structure

After creation, your project will have:

```
my_app/
├── lib/
│   ├── my_app/           # Your Ash resources and domains go here
│   └── my_app.ex         # Application module
├── config/
│   └── config.exs        # Includes Ash domain configuration
├── mix.exs               # Dependencies including Ash
└── test/
```

## Gotchas

- **Archive installation**: The `mix archive.install` commands only need to run once per Elixir installation, not per project
- **Phoenix version**: Ensure your `phx_new` archive is compatible with your Elixir version
- **Database setup**: Projects with `ash_postgres` require running `mix ash.setup` before use
- **Domain configuration**: Ash domains must be listed in `config :my_app, :ash_domains, [...]`

## Next Steps

After creating your project:

1. Define your first domain in `lib/my_app/`
2. Create resources within that domain
3. Configure the data layer if using persistence
4. Generate migrations with `mix ash.codegen`
