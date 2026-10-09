# Lockally::BatchResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **index** | **Integer** |  | [optional] |
| **id** | **String** |  | [optional] |
| **message_id** | **String** |  | [optional] |
| **status** | **String** | \&quot;suppressed\&quot; means every recipient of that slot was on your suppression list, and it carries no id or message_id. \&quot;delivered\&quot; only appears on a test key: the send was simulated, not transmitted. | [optional] |
| **error** | **String** | Present when this message failed; the others are then absent. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::BatchResult.new(
  index: null,
  id: null,
  message_id: null,
  status: null,
  error: null
)
```

