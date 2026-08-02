# Lockally::UpdateCalendarPoliciesRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **max_meeting_duration_mins** | **Integer** |  | [optional] |
| **working_hours_start** | **String** |  | [optional] |
| **working_hours_end** | **String** |  | [optional] |
| **booking_window_days** | **Integer** |  | [optional] |
| **recurring_meeting_limit** | **Integer** |  | [optional] |
| **resource_approval_mode** | **String** |  | [optional] |
| **external_invites_allowed** | **Boolean** |  | [optional] |
| **external_sharing_allowed** | **Boolean** |  | [optional] |
| **public_links_enabled** | **Boolean** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateCalendarPoliciesRequest.new(
  max_meeting_duration_mins: null,
  working_hours_start: null,
  working_hours_end: null,
  booking_window_days: null,
  recurring_meeting_limit: null,
  resource_approval_mode: null,
  external_invites_allowed: null,
  external_sharing_allowed: null,
  public_links_enabled: null
)
```

