# Lockally::GetDomainsStatus200ResponseDomainsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  | [optional] |
| **verified** | **Boolean** |  | [optional] |
| **checks** | [**Array&lt;GetDomainsStatus200ResponseDomainsInnerChecksInner&gt;**](GetDomainsStatus200ResponseDomainsInnerChecksInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetDomainsStatus200ResponseDomainsInner.new(
  domain: null,
  verified: null,
  checks: null
)
```

