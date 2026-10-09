# Lockally::V1MailboxesPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** | Optional; lockally generates if absent. | [optional] |
| **quota_bytes** | **Integer** | 5 GB default. | [optional][default to 5368709120] |

## Example

```ruby
require 'lockally'

instance = Lockally::V1MailboxesPostRequest.new(
  email: alice@acme.com,
  password: null,
  quota_bytes: null
)
```

