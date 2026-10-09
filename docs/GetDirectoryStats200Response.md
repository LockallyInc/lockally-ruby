# Lockally::GetDirectoryStats200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_contacts** | **Integer** |  | [optional] |
| **internal_users** | **Integer** |  | [optional] |
| **external_contacts** | **Integer** |  | [optional] |
| **synced_contacts** | **Integer** |  | [optional] |
| **shared_lists** | **Integer** |  | [optional] |
| **directory_groups** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetDirectoryStats200Response.new(
  total_contacts: null,
  internal_users: null,
  external_contacts: null,
  synced_contacts: null,
  shared_lists: null,
  directory_groups: null
)
```

