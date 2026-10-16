# Lockally::AgentSendResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The Lockally message id. |  |
| **message_id** | **String** | The Internet Message-ID. |  |
| **status** | **String** |  |  |
| **warning** | **String** | Set when the send is accepted but worth noting | [optional] |
| **thread_id** | **String** | The conversation the message joined. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::AgentSendResult.new(
  id: null,
  message_id: null,
  status: null,
  warning: null,
  thread_id: null
)
```

