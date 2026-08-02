# Lockally::UpdateGALSettingsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **gal_enabled** | **Boolean** |  | [optional] |
| **hide_from_directory** | **Boolean** |  | [optional] |
| **department_grouping** | **Boolean** |  | [optional] |
| **search_visibility** | **String** |  | [optional] |
| **include_external_contacts** | **Boolean** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateGALSettingsRequest.new(
  gal_enabled: null,
  hide_from_directory: null,
  department_grouping: null,
  search_visibility: null,
  include_external_contacts: null
)
```

