# Lockally::GetEncryptionStatus200ResponseMailboxesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  | [optional] |
| **has_key** | **Boolean** |  | [optional] |
| **key_created_at** | **Time** |  | [optional] |
| **has_recovery** | **Boolean** |  | [optional] |
| **recovery_set_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetEncryptionStatus200ResponseMailboxesInner.new(
  email: null,
  has_key: null,
  key_created_at: null,
  has_recovery: null,
  recovery_set_at: null
)
```

