# Lockally::AgentSendResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The Lockally message id. | [optional] |
| **status** | **String** |  | [optional] |
| **thread_id** | **String** | The conversation the message joined. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::AgentSendResult.new(
  id: null,
  status: null,
  thread_id: null
)
```

