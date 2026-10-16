# Lockally::CreateAliasRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **alias_address** | **String** |  |  |
| **alias_target** | **String** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateAliasRequest.new(
  alias_address: support@acme.com,
  alias_target: alice@acme.com
)
```

