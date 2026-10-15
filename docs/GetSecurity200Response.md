# Lockally::GetSecurity200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **overall_status** | **String** |  | [optional] |
| **stats** | [**Array&lt;GetSecurity200ResponseStatsInner&gt;**](GetSecurity200ResponseStatsInner.md) |  | [optional] |
| **alerts** | [**Array&lt;GetSecurity200ResponseAlertsInner&gt;**](GetSecurity200ResponseAlertsInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetSecurity200Response.new(
  overall_status: null,
  stats: null,
  alerts: null
)
```

