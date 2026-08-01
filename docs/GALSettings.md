# Lockally::GALSettings

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** |  |  |
| **gal_enabled** | **Boolean** |  |  |
| **hide_from_directory** | **Boolean** |  |  |
| **department_grouping** | **Boolean** |  |  |
| **search_visibility** | **String** |  |  |
| **include_external_contacts** | **Boolean** |  |  |
| **last_index_rebuilt_at** | **Time** |  | [optional] |
| **last_synced_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GALSettings.new(
  tenant_id: null,
  gal_enabled: null,
  hide_from_directory: null,
  department_grouping: null,
  search_visibility: null,
  include_external_contacts: null,
  last_index_rebuilt_at: null,
  last_synced_at: null,
  created_at: null,
  updated_at: null
)
```

