# Lockally::MessageStatsCounts

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **delivered** | **Integer** |  | [optional] |
| **bounced** | **Integer** |  | [optional] |
| **deferred** | **Integer** |  | [optional] |
| **complaint** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::MessageStatsCounts.new(
  delivered: null,
  bounced: null,
  deferred: null,
  complaint: null
)
```

