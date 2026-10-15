# Lockally::GetIPAssignment200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **pool_name** | **String** |  | [optional] |
| **pool_kind** | **String** |  | [optional] |
| **dedicated_ip** | **String** |  | [optional] |
| **assigned_at** | **Time** |  | [optional] |
| **reason** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetIPAssignment200Response.new(
  pool_name: null,
  pool_kind: null,
  dedicated_ip: null,
  assigned_at: null,
  reason: null
)
```

