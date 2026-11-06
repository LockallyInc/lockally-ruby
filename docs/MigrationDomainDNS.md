# Lockally::MigrationDomainDNS

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |
| **mx** | **String** |  |  |
| **spf** | **String** |  |  |
| **dkim** | **String** |  |  |
| **dmarc** | **String** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::MigrationDomainDNS.new(
  domain: null,
  mx: null,
  spf: null,
  dkim: null,
  dmarc: null
)
```

