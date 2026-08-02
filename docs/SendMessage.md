# Lockally::SendMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **String** |  |  |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **text** | **String** |  | [optional] |
| **html** | **String** |  | [optional] |
| **headers** | **Hash&lt;String, String&gt;** |  | [optional] |
| **unsubscribe** | **Boolean** |  | [optional] |
| **template_id** | **String** |  | [optional] |
| **variables** | **Hash&lt;String, String&gt;** |  | [optional] |
| **send_at** | **Time** |  | [optional] |
| **attachments** | [**Array&lt;V1SendPostRequestAttachmentsInner&gt;**](V1SendPostRequestAttachmentsInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::SendMessage.new(
  from: null,
  to: null,
  cc: null,
  bcc: null,
  subject: null,
  text: null,
  html: null,
  headers: null,
  unsubscribe: null,
  template_id: null,
  variables: null,
  send_at: null,
  attachments: null
)
```

