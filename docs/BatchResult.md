# Lockally::BatchResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **index** | **Integer** |  | [optional] |
| **id** | **String** |  | [optional] |
| **message_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
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

