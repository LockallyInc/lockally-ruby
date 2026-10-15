# Lockally::Draft

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **mailbox_id** | **String** |  |  |
| **mailbox** | **String** |  | [optional] |
| **thread_id** | **String** |  | [optional] |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body_text** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **policy_flags** | **Hash&lt;String, Object&gt;** |  |  |
| **reviewed_at** | **Time** |  | [optional] |
| **sent_message_id** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Draft.new(
  id: null,
  mailbox_id: null,
  mailbox: null,
  thread_id: null,
  to: null,
  cc: null,
  subject: null,
  body_text: null,
  status: null,
  policy_flags: null,
  reviewed_at: null,
  sent_message_id: null,
  created_at: null,
  updated_at: null
)
```

