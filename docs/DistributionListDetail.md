# Lockally::DistributionListDetail

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **list_address** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **members** | **Array&lt;String&gt;** |  |  |
| **member_count** | **Integer** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::DistributionListDetail.new(
  id: null,
  tenant_id: null,
  list_address: null,
  name: null,
  created_at: null,
  members: null,
  member_count: null
)
```

