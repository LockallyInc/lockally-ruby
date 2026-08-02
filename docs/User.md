# Lockally::User

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **email** | **String** |  |  |
| **first_name** | **String** |  |  |
| **last_name** | **String** |  |  |
| **title** | **String** |  | [optional] |
| **department** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **mailbox_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::User.new(
  id: null,
  tenant_id: null,
  email: null,
  first_name: null,
  last_name: null,
  title: null,
  department: null,
  status: null,
  created_at: null,
  updated_at: null,
  mailbox_count: null
)
```

