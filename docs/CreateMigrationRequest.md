# Lockally::CreateMigrationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **credential_id** | **String** |  |  |
| **source_provider** | **String** |  |  |
| **settings** | [**MigrationSettings**](MigrationSettings.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateMigrationRequest.new(
  name: null,
  credential_id: null,
  source_provider: null,
  settings: null
)
```

