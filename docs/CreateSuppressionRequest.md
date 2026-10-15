# Lockally::CreateSuppressionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **reason** | **String** |  | [optional][default to &#39;manual&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateSuppressionRequest.new(
  email: null,
  reason: null
)
```

