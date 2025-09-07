# Parse Koala Config

**Internal Action** - Parses KoalaOps configuration files for workflow generation.

## Purpose

This action is used internally by the KoalaOps workflow generator to parse service configurations. It's not intended for direct use in workflows.

## Usage

```yaml
# Internal use only
- uses: KoalaOps/parse-koala-config@v1
  with:
    environment: production
    tag_base: v1.0.0
    config_path: koala.yaml
```

## Inputs

| Input | Description | Required |
|-------|-------------|----------|
| `environment` | Target environment (optional, for environment-specific resolution) | ❌ |
| `tag_base` | Base tag for services (optional, for tag generation) | ❌ |
| `config_path` | Explicit path to config file (optional, auto-detects if not provided) | ❌ |

## Outputs

| Output | Description |
|--------|-------------|
| `version` | Config schema version |
| `services_matrix` | GitHub Actions matrix format with resolved service configurations |
| `services_list` | Simple list of service names |
| `env_clusters` | Environment to cluster mapping |
| `has_multiple_services` | Whether this is a multi-service configuration |
| `service_count` | Number of services defined |
| `config_format` | Format of the config file (yaml/json) |

## Note

This is an internal action used by the KoalaOps platform for configuration parsing during workflow generation. Use the generated workflows instead of calling this action directly.