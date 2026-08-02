# Lockally::Calendar

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **name** | **String** |  |  |
| **color** | **String** |  | [optional] |
| **owner_email** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **visibility** | **String** |  |  |
| **feed_url** | **String** |  | [optional] |
| **event_count** | **Integer** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Calendar.new(
  id: null,
  tenant_id: null,
  name: null,
  color: null,
  owner_email: null,
  description: null,
  visibility: null,
  feed_url: null,
  event_count: null,
  created_at: null,
  updated_at: null
)
```

