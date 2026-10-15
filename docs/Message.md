# Lockally::Message

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **message_id** | **String** | RFC 5322 Message-ID header, including angle brackets. |  |
| **sender** | **String** |  |  |
| **recipients** | **Array&lt;String&gt;** |  |  |
| **subject** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **queued_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **bounce_reason** | **String** |  | [optional] |
| **size_bytes** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Message.new(
  id: null,
  tenant_id: null,
  message_id: null,
  sender: null,
  recipients: null,
  subject: null,
  status: null,
  queued_at: null,
  updated_at: null,
  bounce_reason: null,
  size_bytes: null
)
```

