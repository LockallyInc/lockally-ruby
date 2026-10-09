# Lockally::V1SendPost200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Present on a test-mode send; absent when suppressed. | [optional] |
| **message_id** | **String** | RFC 5322 Message-ID. On a test send the domain is test.lockally.com. Absent when suppressed. | [optional] |
| **status** | **String** |  |  |
| **warning** | **String** | On a suppressed send, explains that nothing was sent. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::V1SendPost200Response.new(
  id: null,
  message_id: null,
  status: null,
  warning: null
)
```

