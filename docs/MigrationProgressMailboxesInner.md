# Lockally::MigrationProgressMailboxesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source_email** | **String** |  |  |
| **dest_email** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **source_message_count** | **Integer** |  | [optional] |
| **synced_message_count** | **Integer** |  |  |
| **failed_message_count** | **Integer** |  |  |
| **percent_complete** | **Float** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationProgressMailboxesInner.new(
  source_email: null,
  dest_email: null,
  status: null,
  source_message_count: null,
  synced_message_count: null,
  failed_message_count: null,
  percent_complete: null
)
```

