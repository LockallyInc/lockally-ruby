# Lockally::MigrationCredential

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **provider** | **String** |  |  |
| **encryption_key_id** | **String** |  | [optional] |
| **label** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationCredential.new(
  id: null,
  tenant_id: null,
  provider: null,
  encryption_key_id: null,
  label: null,
  created_at: null,
  updated_at: null
)
```

