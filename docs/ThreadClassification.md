# Lockally::ThreadClassification

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **cached** | **Boolean** | True when a previous classification was reused. | [optional] |
| **classification** | [**Classification**](Classification.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ThreadClassification.new(
  thread_id: null,
  cached: null,
  classification: null
)
```

