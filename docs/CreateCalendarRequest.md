# Lockally::CreateCalendarRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **color** | **String** |  | [optional] |
| **owner_email** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **visibility** | **String** |  | [optional][default to &#39;tenant&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateCalendarRequest.new(
  name: null,
  color: null,
  owner_email: null,
  description: null,
  visibility: null
)
```

