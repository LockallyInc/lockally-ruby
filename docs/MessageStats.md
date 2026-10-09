# Lockally::MessageStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **window** | [**MessageStatsWindow**](MessageStatsWindow.md) |  | [optional] |
| **domain** | **String** |  | [optional] |
| **sent** | **Integer** |  | [optional] |
| **counts** | [**MessageStatsCounts**](MessageStatsCounts.md) |  | [optional] |
| **rates** | [**MessageStatsRates**](MessageStatsRates.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::MessageStats.new(
  window: null,
  domain: null,
  sent: null,
  counts: null,
  rates: null
)
```

