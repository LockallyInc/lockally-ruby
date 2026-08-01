# Lockally::GetUserInsights200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recently_added** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **recently_suspended** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **inactive_30d** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **seats_used** | **Integer** |  | [optional] |
| **seats_alloc** | **Integer** |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetUserInsights200Response.new(
  recently_added: null,
  recently_suspended: null,
  inactive_30d: null,
  seats_used: null,
  seats_alloc: null,
  generated_at: null
)
```

