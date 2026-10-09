# Lockally::UpdateMigrationMailboxRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dest_email** | **String** |  | [optional] |
| **status** | **String** | Can only be set to \&quot;skipped\&quot;. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateMigrationMailboxRequest.new(
  dest_email: null,
  status: null
)
```

