# Lockally::GetStorage200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_bytes** | **Integer** |  | [optional] |
| **alloc_bytes** | **Integer** |  | [optional] |
| **per_seat_bytes** | **Integer** |  | [optional] |
| **top_mailboxes** | [**Array&lt;GetStorage200ResponseTopMailboxesInner&gt;**](GetStorage200ResponseTopMailboxesInner.md) |  | [optional] |
| **top_messages** | [**Array&lt;GetStorage200ResponseTopMessagesInner&gt;**](GetStorage200ResponseTopMessagesInner.md) |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetStorage200Response.new(
  total_bytes: null,
  alloc_bytes: null,
  per_seat_bytes: null,
  top_mailboxes: null,
  top_messages: null,
  generated_at: null
)
```

