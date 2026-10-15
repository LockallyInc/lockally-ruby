# Lockally::Inbox

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **email** | **String** |  |  |
| **last_message_at** | **Time** |  | [optional] |
| **thread_count** | **Integer** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Inbox.new(
  id: null,
  email: null,
  last_message_at: null,
  thread_count: null
)
```

