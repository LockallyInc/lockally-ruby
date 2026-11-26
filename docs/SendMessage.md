# Lockally::SendMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **String** | Sender address, alone or as &#x60;Acme Orders &lt;orders@acme.com&gt;&#x60;. |  |
| **from_name** | **String** | Display name shown next to &#x60;from&#x60;. Must match a name given in &#x60;from&#x60;. Cannot contain &#x60;@&#x60; or control characters. | [optional] |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **text** | **String** |  | [optional] |
| **html** | **String** |  | [optional] |
| **headers** | **Hash&lt;String, String&gt;** |  | [optional] |
| **reply_to** | **String** | Where replies go. Required when &#x60;from&#x60; has no mailbox behind it. The named form &#x60;Acme Support &lt;a@b.com&gt;&#x60; is also accepted. | [optional] |
| **reply_to_name** | **String** | Display name shown on &#x60;Reply-To&#x60;. Ignored without &#x60;reply_to&#x60;. | [optional] |
| **unsubscribe** | **Boolean** |  | [optional] |
| **template_id** | **String** |  | [optional] |
| **variables** | **Hash&lt;String, String&gt;** |  | [optional] |
| **send_at** | **Time** |  | [optional] |
| **attachments** | [**Array&lt;SendEmailRequestAttachmentsInner&gt;**](SendEmailRequestAttachmentsInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::SendMessage.new(
  from: null,
  from_name: null,
  to: null,
  cc: null,
  bcc: null,
  subject: null,
  text: null,
  html: null,
  headers: null,
  reply_to: null,
  reply_to_name: null,
  unsubscribe: null,
  template_id: null,
  variables: null,
  send_at: null,
  attachments: null
)
```

