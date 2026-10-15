# Lockally::CreateMailboxRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** | Optional; lockally generates if absent. | [optional] |
| **quota_bytes** | **Integer** | 5 GB default. | [optional][default to 5368709120] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateMailboxRequest.new(
  email: alice@acme.com,
  password: null,
  quota_bytes: null
)
```

