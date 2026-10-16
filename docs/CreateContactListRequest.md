# Lockally::CreateContactListRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **visibility** | **String** |  | [optional][default to &#39;company_wide&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateContactListRequest.new(
  name: null,
  description: null,
  visibility: null
)
```

