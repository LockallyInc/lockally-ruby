# Lockally::GetCalendarOverview200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_calendars** | **Integer** |  | [optional] |
| **active_calendars** | **Integer** | Calendars with an event created, edited or held in the last 30 days. | [optional] |
| **shared_calendars** | **Integer** | Calendars visible to the whole organization. | [optional] |
| **events_this_month** | **Integer** | Events on every calendar, in the account&#39;s own timezone. | [optional] |
| **upcoming_org_events** | **Integer** | Future events on organization-visible calendars. | [optional] |
| **bookable_resources** | **Integer** | Resources that are not disabled. | [optional] |
| **access_granted** | **Integer** | People who own a calendar or are named on one. | [optional] |
| **access_org_wide** | **Integer** | Everyone who can see an organization calendar; 0 when none exists. | [optional] |
| **activity** | [**Array&lt;GetCalendarOverview200ResponseActivityInner&gt;**](GetCalendarOverview200ResponseActivityInner.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetCalendarOverview200Response.new(
  total_calendars: null,
  active_calendars: null,
  shared_calendars: null,
  events_this_month: null,
  upcoming_org_events: null,
  bookable_resources: null,
  access_granted: null,
  access_org_wide: null,
  activity: null
)
```

