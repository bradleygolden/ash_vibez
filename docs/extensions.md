# Ash Extensions

This guide lists common Ash extensions and how to discover more.

## Quick Reference

Common extensions for `--install` flag:

```bash
# Data layers
ash_postgres, ash_sqlite

# Web/API
ash_phoenix, ash_json_api, ash_graphql

# Auth
ash_authentication, ash_authentication_phoenix

# Background jobs
ash_oban
```

## Discovering Extensions

The Ash ecosystem is actively growing. To find all available extensions:

### Method 1: Hex.pm Search

Fetch and parse:
```
https://hex.pm/packages?search=ash&sort=recent_downloads
```

Look for packages starting with `ash_` that are official Ash extensions.

### Method 2: Ash HQ Homepage

Fetch and parse:
```
https://ash-hq.org
```

The homepage lists featured extensions with descriptions.

## Common Extensions Reference

### Data Layers

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshPostgres | `ash_postgres` | PostgreSQL database |
| AshSqlite | `ash_sqlite` | SQLite database |
| AshCsv | `ash_csv` | CSV file data |

### Web & API

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshPhoenix | `ash_phoenix` | Phoenix integration, forms, LiveView helpers |
| AshJsonApi | `ash_json_api` | REST API following JSON:API specification |
| AshGraphql | `ash_graphql` | GraphQL API generation |
| AshAdmin | `ash_admin` | Auto-generated admin UI (Phoenix LiveView) |

### Authentication & Security

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshAuthentication | `ash_authentication` | User authentication (passwords, OAuth, magic links) |
| AshAuthenticationPhoenix | `ash_authentication_phoenix` | Phoenix UI components for auth |
| AshCloak | `ash_cloak` | Attribute encryption/decryption |
| AshRateLimiter | `ash_rate_limiter` | Rate limiting for actions |

### Data Management

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshArchival | `ash_archival` | Soft deletion (archive instead of delete) |
| AshPaperTrail | `ash_paper_trail` | Audit logs, change history |
| AshStateMachine | `ash_state_machine` | State machine for resources |
| AshEvents | `ash_events` | Event sourcing patterns |

### Specialized

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshOban | `ash_oban` | Background job processing |
| AshAi | `ash_ai` | LLM/AI integration |
| AshMoney | `ash_money` | Money/currency types |
| AshDoubleEntry | `ash_double_entry` | Double-entry accounting |
| AshGeo | `ash_geo` | Geospatial data types |

### Observability

| Package | Install Name | Purpose |
|---------|--------------|---------|
| AshAppsignal | `ash_appsignal` | AppSignal APM integration |

## Installation Patterns

### Single Extension

```bash
mix igniter.new my_app --install ash,ash_postgres
```

### Multiple Extensions

```bash
mix igniter.new my_app --install ash,ash_postgres,ash_phoenix,ash_authentication --with phx.new
```

### Adding to Existing Project

```bash
mix igniter.install ash_oban
```

## Extension Compatibility

Most extensions work together, but note:

- **Data layers are exclusive**: Use only one of `ash_postgres`, `ash_sqlite`, etc.
- **Phoenix extensions require Phoenix**: `ash_phoenix`, `ash_authentication_phoenix`, `ash_admin` need a Phoenix project
- **Some extensions have dependencies**: `ash_authentication_phoenix` requires `ash_authentication`

## Checking for New Extensions

Extensions are published to Hex.pm. To find the latest:

1. Search Hex.pm for packages matching `ash_*`
2. Check the package's Hex page for compatibility with your Ash version
3. Review the package documentation on HexDocs
