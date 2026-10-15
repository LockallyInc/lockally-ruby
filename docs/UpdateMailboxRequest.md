# Lockally::UpdateMailboxRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **password** | **String** |  | [optional] |
| **quota_bytes** | **Integer** |  | [optional] |
| **disabled** | **Boolean** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateMailboxRequest.new(
  password: null,
  quota_bytes: null,
  disabled: null
)
```

