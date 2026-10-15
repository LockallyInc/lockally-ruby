# Lockally::DirectoryPermissions

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** |  |  |
| **contact_view_access** | **String** |  |  |
| **contact_edit_access** | **String** |  |  |
| **list_manage_access** | **String** |  |  |
| **external_sharing** | **String** |  |  |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::DirectoryPermissions.new(
  tenant_id: null,
  contact_view_access: null,
  contact_edit_access: null,
  list_manage_access: null,
  external_sharing: null,
  created_at: null,
  updated_at: null
)
```

