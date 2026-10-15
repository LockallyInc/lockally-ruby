# Lockally::ContactLookup

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **known** | **Boolean** |  |  |
| **internal** | **Boolean** | True when the address is one of the tenant&#39;s own mailboxes. |  |
| **contact** | [**ContactLookupContact**](ContactLookupContact.md) |  | [optional] |
| **history** | [**ContactLookupHistory**](ContactLookupHistory.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::ContactLookup.new(
  email: null,
  known: null,
  internal: null,
  contact: null,
  history: null
)
```

