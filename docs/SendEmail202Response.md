# Lockally::SendEmail202Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Lockally identifier; use with GET /v1/messages/{id}. |  |
| **message_id** | **String** | RFC 5322 Message-ID (with angle brackets). |  |
| **status** | **String** | \&quot;scheduled\&quot; when send_at is in the future. |  |
| **warning** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::SendEmail202Response.new(
  id: null,
  message_id: null,
  status: null,
  warning: null
)
```

