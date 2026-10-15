# Lockally::InjectionRisk

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **flagged** | **Boolean** |  | [optional] |
| **signals** | **Array&lt;String&gt;** | The phrases that tripped the check. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::InjectionRisk.new(
  flagged: null,
  signals: null
)
```

