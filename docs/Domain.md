# Lockally::Domain

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **domain** | **String** |  |  |
| **verification_token** | **String** |  |  |
| **verified** | **Boolean** |  |  |
| **verified_at** | **Time** |  | [optional] |
| **dkim_selector** | **String** |  |  |
| **dkim_public_record** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **records** | [**Array&lt;DNSRecord&gt;**](DNSRecord.md) | DNS records the tenant must publish under their own DNS. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Domain.new(
  id: null,
  tenant_id: null,
  domain: acme.com,
  verification_token: lkv-zyj4p5qbv6i4rjm7s3wrrkr3jzo3lrvy,
  verified: null,
  verified_at: null,
  dkim_selector: lockally,
  dkim_public_record: v&#x3D;DKIM1; k&#x3D;rsa; p&#x3D;MIIBIjAN...,
  created_at: null,
  records: null
)
```

