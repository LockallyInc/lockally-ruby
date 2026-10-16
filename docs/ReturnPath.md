# Lockally::ReturnPath

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  |  |
| **host** | **String** |  |  |
| **records** | [**Array&lt;DNSRecord&gt;**](DNSRecord.md) |  |  |
| **check** | [**ReturnPathCheck**](ReturnPathCheck.md) |  | [optional] |
| **requested_at** | **Time** |  | [optional] |
| **verified_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ReturnPath.new(
  status: null,
  host: bounces.acme.com,
  records: null,
  check: null,
  requested_at: null,
  verified_at: null
)
```

