# Lockally::SimulatedInbound

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  | [optional] |
| **message_id** | **String** |  | [optional] |
| **annotations** | [**Annotations**](Annotations.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::SimulatedInbound.new(
  thread_id: null,
  message_id: null,
  annotations: null
)
```

