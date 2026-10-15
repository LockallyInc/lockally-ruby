# Lockally::Mailbox

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **domain_id** | **String** |  |  |
| **email** | **String** |  |  |
| **quota_bytes** | **Integer** |  |  |
| **disabled** | **Boolean** |  |  |
| **disabled_at** | **Time** |  | [optional] |
| **soft_deleted_at** | **Time** |  | [optional] |
| **hard_delete_after** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **password** | **String** | ONLY present on POST response when lockally generated the password. Shown once. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Mailbox.new(
  id: null,
  tenant_id: null,
  domain_id: null,
  email: null,
  quota_bytes: null,
  disabled: null,
  disabled_at: null,
  soft_deleted_at: null,
  hard_delete_after: null,
  created_at: null,
  password: null
)
```

