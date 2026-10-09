# Lockally::UpdateDirectoryPermissionsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **contact_view_access** | **String** |  | [optional] |
| **contact_edit_access** | **String** |  | [optional] |
| **list_manage_access** | **String** |  | [optional] |
| **external_sharing** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateDirectoryPermissionsRequest.new(
  contact_view_access: null,
  contact_edit_access: null,
  list_manage_access: null,
  external_sharing: null
)
```

