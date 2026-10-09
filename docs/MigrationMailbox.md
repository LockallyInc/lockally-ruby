# Lockally::MigrationMailbox

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **migration_id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **source_email** | **String** |  |  |
| **dest_email** | **String** |  | [optional] |
| **dest_mailbox_id** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **source_message_count** | **Integer** |  | [optional] |
| **synced_message_count** | **Integer** |  |  |
| **failed_message_count** | **Integer** |  |  |
| **source_size_bytes** | **Integer** |  | [optional] |
| **synced_size_bytes** | **Integer** |  | [optional] |
| **last_synced_uid** | **String** |  | [optional] |
| **last_synced_at** | **Time** |  | [optional] |
| **error_message** | **String** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **completed_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationMailbox.new(
  id: null,
  migration_id: null,
  tenant_id: null,
  source_email: null,
  dest_email: null,
  dest_mailbox_id: null,
  status: null,
  source_message_count: null,
  synced_message_count: null,
  failed_message_count: null,
  source_size_bytes: null,
  synced_size_bytes: null,
  last_synced_uid: null,
  last_synced_at: null,
  error_message: null,
  started_at: null,
  completed_at: null,
  created_at: null,
  updated_at: null
)
```

