# Lockally::ThreadMessageBody

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **mailbox** | **String** |  |  |
| **message** | [**ThreadMessage**](ThreadMessage.md) |  |  |
| **body** | [**ThreadMessageBodyBody**](ThreadMessageBodyBody.md) |  | [optional] |
| **body_unavailable** | **String** | Present instead of body when the message could not be located in the mailbox. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ThreadMessageBody.new(
  thread_id: null,
  mailbox: null,
  message: null,
  body: null,
  body_unavailable: null
)
```

