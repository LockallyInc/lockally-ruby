# Lockally::V1ApiKeysPost201Response

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
| **secret** | **String** | The full &#x60;lk_live_&lt;prefix&gt;_&lt;secret&gt;&#x60; token. Shown ONCE. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::V1ApiKeysPost201Response.new(
  id: null,
  tenant_id: null,
  prefix: fbl73bhj,
  scopes: null,
  label: ci-pipeline,
  last_used_at: null,
  revoked_at: null,
  created_at: null,
  secret: lk_live_fbl73bhj_sfvqy7y757cnvu33bgqdpyrrhq3tyyf3
)
```

