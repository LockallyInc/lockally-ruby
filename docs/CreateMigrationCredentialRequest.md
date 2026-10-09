# Lockally::CreateMigrationCredentialRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  |  |
| **label** | **String** |  | [optional] |
| **credentials** | [**CreateMigrationCredentialRequestCredentials**](CreateMigrationCredentialRequestCredentials.md) |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateMigrationCredentialRequest.new(
  provider: null,
  label: null,
  credentials: null
)
```

