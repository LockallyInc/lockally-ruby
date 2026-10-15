# Lockally::Migration

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **credential_id** | **String** |  |  |
| **name** | **String** |  |  |
| **status** | **String** |  |  |
| **source_provider** | **String** |  |  |
| **source_summary** | **String** |  | [optional] |
| **settings** | [**MigrationSettings**](MigrationSettings.md) |  | [optional] |
| **error_message** | **String** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **completed_at** | **Time** |  | [optional] |
| **mailbox_count** | **Integer** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Migration.new(
  id: null,
  tenant_id: null,
  credential_id: null,
  name: null,
  status: null,
  source_provider: null,
  source_summary: null,
  settings: null,
  error_message: null,
  started_at: null,
  completed_at: null,
  mailbox_count: null,
  created_at: null,
  updated_at: null
)
```

