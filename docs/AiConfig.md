# Lockally::AiConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mode** | **String** |  |  |
| **model** | **String** |  |  |
| **byok_key_hint** | **String** |  | [optional] |
| **units_balance** | **Integer** |  | [optional] |
| **units_available** | **Boolean** | True when a platform model key is configured. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::AiConfig.new(
  mode: null,
  model: null,
  byok_key_hint: null,
  units_balance: null,
  units_available: null
)
```

