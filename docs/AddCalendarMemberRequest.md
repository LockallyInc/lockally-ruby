# Lockally::AddCalendarMemberRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_email** | **String** |  |  |
| **role** | **String** |  | [optional][default to &#39;viewer&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::AddCalendarMemberRequest.new(
  user_email: null,
  role: null
)
```

