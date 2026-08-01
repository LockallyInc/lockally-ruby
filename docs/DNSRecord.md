# Lockally::DNSRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  |  |
| **name** | **String** |  |  |
| **value** | **String** |  |  |
| **ttl** | **Integer** |  |  |
| **priority** | **Integer** | MX records only. | [optional] |
| **purpose** | **String** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::DNSRecord.new(
  type: null,
  name: null,
  value: null,
  ttl: 300,
  priority: null,
  purpose: null
)
```

