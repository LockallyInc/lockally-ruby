# Lockally::TrackingPolicy

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **track_opens** | **Boolean** |  |  |
| **track_clicks** | **Boolean** |  |  |
| **updated_at** | **Time** | Absent until a policy has been set. | [optional] |
| **configured** | **Boolean** | Whether this deployment holds a tracking signing secret. False means tracking cannot work whatever the flags say. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::TrackingPolicy.new(
  track_opens: null,
  track_clicks: null,
  updated_at: null,
  configured: null
)
```

