# Lockally::GetEncryptionStatus200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **eligible** | **Boolean** |  | [optional] |
| **active** | **Boolean** |  | [optional] |
| **mailboxes** | [**Array&lt;GetEncryptionStatus200ResponseMailboxesInner&gt;**](GetEncryptionStatus200ResponseMailboxesInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetEncryptionStatus200Response.new(
  eligible: null,
  active: null,
  mailboxes: null
)
```

