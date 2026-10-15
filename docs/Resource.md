# Lockally::Resource

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **name** | **String** |  |  |
| **type** | **String** |  |  |
| **capacity** | **Integer** |  | [optional] |
| **status** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Resource.new(
  id: null,
  tenant_id: null,
  name: null,
  type: null,
  capacity: null,
  status: null,
  created_at: null,
  updated_at: null
)
```

