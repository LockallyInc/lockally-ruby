# Lockally::AddSharedMemberRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **member_email** | **String** |  |  |
| **role** | **String** |  | [optional][default to &#39;member&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::AddSharedMemberRequest.new(
  member_email: null,
  role: null
)
```

