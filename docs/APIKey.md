# Lockally::APIKey

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **prefix** | **String** | 8-char public prefix; safe to store and display. |  |
| **scopes** | **Array&lt;String&gt;** |  |  |
| **label** | **String** |  |  |
| **last_used_at** | **Time** |  | [optional] |
| **revoked_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::APIKey.new(
  id: null,
  tenant_id: null,
  prefix: fbl73bhj,
  scopes: null,
  label: ci-pipeline,
  last_used_at: null,
  revoked_at: null,
  created_at: null
)
```

