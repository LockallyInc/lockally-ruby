# Lockally::SimulatedInbound

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **simulated** | **Boolean** |  | [optional] |
| **indexed** | **Boolean** | True when the message was adopted into a thread. | [optional] |
| **thread_id** | **String** |  | [optional] |
| **message_id** | **String** |  | [optional] |
| **rfc_message_id** | **String** |  | [optional] |
| **annotations** | [**Annotations**](Annotations.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::SimulatedInbound.new(
  simulated: null,
  indexed: null,
  thread_id: null,
  message_id: null,
  rfc_message_id: null,
  annotations: null
)
```

