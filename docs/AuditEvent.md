# Lockally::AuditEvent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  | [optional] |
| **event_type** | **String** |  | [optional] |
| **detail** | **String** |  | [optional] |
| **ip** | **String** |  | [optional] |
| **time** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::AuditEvent.new(
  email: null,
  event_type: null,
  detail: null,
  ip: null,
  time: null
)
```

