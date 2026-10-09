# Lockally::MessageStatsRates

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **delivered** | **Float** |  | [optional] |
| **bounced** | **Float** |  | [optional] |
| **deferred** | **Float** |  | [optional] |
| **complaint** | **Float** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::MessageStatsRates.new(
  delivered: null,
  bounced: null,
  deferred: null,
  complaint: null
)
```

