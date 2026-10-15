# Lockally::DraftResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |
| **status** | **String** |  |  |
| **policy_flags** | **Hash&lt;String, Object&gt;** |  |  |
| **thread_id** | **String** |  | [optional] |
| **sent** | [**AgentSendResult**](AgentSendResult.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::DraftResult.new(
  draft_id: null,
  status: null,
  policy_flags: null,
  thread_id: null,
  sent: null
)
```

