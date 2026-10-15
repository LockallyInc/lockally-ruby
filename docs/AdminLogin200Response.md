# Lockally::AdminLogin200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |
| **expires_at** | **Time** |  |  |
| **admin** | [**Admin**](Admin.md) |  |  |
| **tenant** | [**Tenant**](Tenant.md) |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::AdminLogin200Response.new(
  token: adm_sess_...,
  expires_at: null,
  admin: null,
  tenant: null
)
```

