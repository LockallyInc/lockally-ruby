# Lockally::UpdateAdminRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **password** | **String** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |
| **disabled** | **Boolean** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateAdminRequest.new(
  password: null,
  display_name: null,
  role: null,
  disabled: null
)
```

