# Lockally::UpdateCalendarEventRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **location** | **String** |  | [optional] |
| **starts_at** | **Time** |  | [optional] |
| **ends_at** | **Time** |  | [optional] |
| **all_day** | **Boolean** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateCalendarEventRequest.new(
  title: null,
  description: null,
  location: null,
  starts_at: null,
  ends_at: null,
  all_day: null
)
```

