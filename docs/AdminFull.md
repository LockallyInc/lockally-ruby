# Lockally::AdminFull

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
| **disabled** | **Boolean** |  |  |
| **disabled_at** | **Time** |  | [optional] |
| **password** | **String** | Present ONLY on POST response when lockally generated the password. Shown once. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::AdminFull.new(
  id: null,
  tenant_id: null,
  email: null,
  display_name: null,
  role: null,
  last_login_at: null,
  created_at: null,
  disabled: null,
  disabled_at: null,
  password: null
)
```

