# Lockally::UpdateApiKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **label** | **String** | Free-text identifier shown in the dashboard. | [optional] |
| **scopes** | **Array&lt;String&gt;** | Replaces the key&#39;s scopes entirely. | [optional] |
| **expires_at** | **Time** | A future timestamp to set an expiry, or null to remove one. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateApiKeyRequest.new(
  label: null,
  scopes: null,
  expires_at: null
)
```

