# Lockally::MigrationEvent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **migration_id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **mailbox_id** | **String** |  | [optional] |
| **event_type** | **String** |  |  |
| **actor** | **String** |  |  |
| **old_status** | **String** |  | [optional] |
| **new_status** | **String** |  | [optional] |
| **detail** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationEvent.new(
  id: null,
  migration_id: null,
  tenant_id: null,
  mailbox_id: null,
  event_type: null,
  actor: null,
  old_status: null,
  new_status: null,
  detail: null,
  created_at: null
)
```

