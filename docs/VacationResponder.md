# Lockally::VacationResponder

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox_email** | **String** |  |  |
| **enabled** | **Boolean** |  |  |
| **params** | [**VacationParams**](VacationParams.md) |  |  |
| **script** | **String** | Pre-rendered Sieve script (RFC 5230). |  |
| **synced_at** | **Time** | Null &#x3D; stored on lockally but not yet pushed to the mail server. | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::VacationResponder.new(
  mailbox_email: null,
  enabled: null,
  params: null,
  script: null,
  synced_at: null,
  created_at: null,
  updated_at: null
)
```

