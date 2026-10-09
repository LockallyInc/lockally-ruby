# Lockally::GetUserInsights200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recently_added** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **recently_suspended** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **inactive_30d** | [**Array&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] |
| **seats_used** | **Integer** |  | [optional] |
| **seats_alloc** | **Integer** |  | [optional] |
| **seats_capped** | **Boolean** | True only on tiers with a hard seat cap (Free, Founder). On unlimited/per-seat tiers seats_alloc merely tracks the live mailbox count, so seats_used &#x3D;&#x3D; seats_alloc is normal and must not be read as &#39;at capacity&#39;. | [optional] |
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
  seats_capped: null,
  generated_at: null
)
```

