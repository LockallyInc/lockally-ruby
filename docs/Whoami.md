# Lockally::Whoami

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant** | [**WhoamiTenant**](WhoamiTenant.md) |  |  |
| **scopes** | **Array&lt;String&gt;** |  |  |
| **auth** | **String** |  |  |
| **key** | [**WhoamiKey**](WhoamiKey.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Whoami.new(
  tenant: null,
  scopes: null,
  auth: null,
  key: null
)
```

