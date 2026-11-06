# Lockally::CreateApiKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **label** | **String** | Free-text identifier shown in the dashboard. |  |
| **scopes** | **Array&lt;String&gt;** | Allowed scopes on this key. |  |
| **test** | **Boolean** | Issue a test key (&#x60;lk_test_&#x60; prefix). A test key accepts sends, records them and fires a simulated delivery webhook without sending mail, and counts against no limit or allowance.  | [optional][default to false] |
| **expires_at** | **Time** | Optional. When the key stops authenticating. Omit it for a key that does not expire. Must be in the future: an expiry already past would mint a key that fails its first request.  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateApiKeyRequest.new(
  label: ci-pipeline,
  scopes: null,
  test: null,
  expires_at: null
)
```

