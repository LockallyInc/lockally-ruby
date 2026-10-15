# Lockally::ThreadMessageBody

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **direction** | **String** |  |  |
| **rfc_message_id** | **String** | The Internet Message-ID |  |
| **in_reply_to** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **from** | **String** |  |  |
| **to** | **Array&lt;String&gt;** |  |  |
| **snippet** | **String** |  | [optional] |
| **has_attachments** | **Boolean** |  |  |
| **attachments** | [**Array&lt;Attachment&gt;**](Attachment.md) |  | [optional] |
| **annotations** | [**Annotations**](Annotations.md) |  | [optional] |
| **received_at** | **Time** |  |  |
| **body** | [**ThreadMessageBodyAllOfBody**](ThreadMessageBodyAllOfBody.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ThreadMessageBody.new(
  id: null,
  direction: null,
  rfc_message_id: null,
  in_reply_to: null,
  subject: null,
  from: null,
  to: null,
  snippet: null,
  has_attachments: null,
  attachments: null,
  annotations: null,
  received_at: null,
  body: null
)
```

