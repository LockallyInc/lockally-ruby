# Lockally::V1ApiKeysPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **label** | **String** | Free-text identifier shown in the dashboard. |  |
| **scopes** | **Array&lt;String&gt;** | Allowed scopes on this key. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::V1ApiKeysPostRequest.new(
  label: ci-pipeline,
  scopes: null
)
```

