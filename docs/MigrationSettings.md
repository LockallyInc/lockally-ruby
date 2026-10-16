# Lockally::MigrationSettings

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **max_concurrent_mailboxes** | **Integer** |  | [optional] |
| **max_concurrent_messages** | **Integer** |  | [optional] |
| **source_rate_limit** | **Integer** |  | [optional] |
| **batch_size** | **Integer** |  | [optional] |
| **skip_folders** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationSettings.new(
  max_concurrent_mailboxes: null,
  max_concurrent_messages: null,
  source_rate_limit: null,
  batch_size: null,
  skip_folders: null
)
```

