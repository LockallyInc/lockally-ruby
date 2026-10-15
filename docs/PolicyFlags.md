# Lockally::PolicyFlags

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **always_approve** | **Boolean** |  | [optional] |
| **injection_risk** | **Boolean** |  | [optional] |
| **new_recipient** | **Array&lt;String&gt;** |  | [optional] |
| **new_thread** | **Boolean** |  | [optional] |
| **pii** | **Array&lt;String&gt;** |  | [optional] |
| **recipient_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::PolicyFlags.new(
  always_approve: null,
  injection_risk: null,
  new_recipient: null,
  new_thread: null,
  pii: null,
  recipient_count: null
)
```

