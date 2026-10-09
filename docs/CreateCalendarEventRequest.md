# Lockally::CreateCalendarEventRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **location** | **String** |  | [optional] |
| **starts_at** | **Time** |  |  |
| **ends_at** | **Time** |  |  |
| **all_day** | **Boolean** |  | [optional][default to false] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateCalendarEventRequest.new(
  title: null,
  description: null,
  location: null,
  starts_at: null,
  ends_at: null,
  all_day: null
)
```

