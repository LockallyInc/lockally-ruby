# Lockally::MigrationProgress

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **migration_id** | **String** |  |  |
| **status** | **String** |  |  |
| **total_mailboxes** | **Integer** |  |  |
| **completed_mailboxes** | **Integer** |  |  |
| **failed_mailboxes** | **Integer** |  |  |
| **total_messages** | **Integer** |  |  |
| **synced_messages** | **Integer** |  |  |
| **failed_messages** | **Integer** |  |  |
| **percent_complete** | **Float** |  |  |
| **mailboxes** | [**Array&lt;MigrationProgressMailboxesInner&gt;**](MigrationProgressMailboxesInner.md) |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationProgress.new(
  migration_id: null,
  status: null,
  total_mailboxes: null,
  completed_mailboxes: null,
  failed_mailboxes: null,
  total_messages: null,
  synced_messages: null,
  failed_messages: null,
  percent_complete: null,
  mailboxes: null
)
```

