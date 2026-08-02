# Lockally::VacationParams

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subject** | **String** |  |  |
| **body** | **String** |  |  |
| **starts_at** | **Time** |  | [optional] |
| **ends_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::VacationParams.new(
  subject: Out of office until June 5,
  body: Hi! I&#39;m away until June 5. For urgent matters please contact ...,
  starts_at: null,
  ends_at: null
)
```

