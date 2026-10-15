# Lockally::Whoami

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** |  | [optional] |
| **tenant** | **String** |  | [optional] |
| **label** | **String** | The API key&#39;s label. | [optional] |
| **scopes** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Whoami.new(
  tenant_id: null,
  tenant: null,
  label: null,
  scopes: null
)
```

