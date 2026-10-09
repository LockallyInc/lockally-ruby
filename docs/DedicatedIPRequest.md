# Lockally::DedicatedIPRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **status** | **String** |  |  |
| **note** | **String** |  | [optional] |
| **admin_note** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **resolved_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::DedicatedIPRequest.new(
  id: null,
  tenant_id: null,
  status: null,
  note: null,
  admin_note: null,
  created_at: null,
  resolved_at: null
)
```

