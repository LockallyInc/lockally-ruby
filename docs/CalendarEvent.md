# Lockally::CalendarEvent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **calendar_id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **uid** | **String** |  |  |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **location** | **String** |  | [optional] |
| **starts_at** | **Time** |  |  |
| **ends_at** | **Time** |  |  |
| **all_day** | **Boolean** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CalendarEvent.new(
  id: null,
  calendar_id: null,
  tenant_id: null,
  uid: null,
  title: null,
  description: null,
  location: null,
  starts_at: null,
  ends_at: null,
  all_day: null,
  created_at: null,
  updated_at: null
)
```

