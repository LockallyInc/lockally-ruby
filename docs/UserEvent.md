# Lockally::UserEvent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  | [optional] |
| **event_at** | **Time** |  | [optional] |
| **days_inactive** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UserEvent.new(
  email: null,
  event_at: null,
  days_inactive: null
)
```

