# Lockally::Admin

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **email** | **String** |  |  |
| **display_name** | **String** |  | [optional] |
| **role** | **String** |  |  |
| **last_login_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Admin.new(
  id: null,
  tenant_id: null,
  email: null,
  display_name: null,
  role: null,
  last_login_at: null,
  created_at: null
)
```

