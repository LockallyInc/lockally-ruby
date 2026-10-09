# Lockally::V1AliasesPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **alias_address** | **String** |  |  |
| **alias_target** | **String** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::V1AliasesPostRequest.new(
  alias_address: support@acme.com,
  alias_target: alice@acme.com
)
```

