# Lockally::ThreadSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **subject** | **String** |  | [optional] |
| **participants** | **Array&lt;String&gt;** |  |  |
| **message_count** | **Integer** |  |  |
| **last_message_at** | **Time** |  | [optional] |
| **last_direction** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ThreadSummary.new(
  id: null,
  subject: null,
  participants: null,
  message_count: null,
  last_message_at: null,
  last_direction: null
)
```

