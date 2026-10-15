# Lockally::GetCalendarSecurity200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_calendars** | **Integer** |  | [optional] |
| **public_calendars** | **Integer** |  | [optional] |
| **private_calendars** | **Integer** |  | [optional] |
| **total_members** | **Integer** |  | [optional] |
| **delegated_access** | [**Array&lt;GetCalendarSecurity200ResponseDelegatedAccessInner&gt;**](GetCalendarSecurity200ResponseDelegatedAccessInner.md) |  | [optional] |
| **public_calendar_list** | [**Array&lt;GetCalendarSecurity200ResponsePublicCalendarListInner&gt;**](GetCalendarSecurity200ResponsePublicCalendarListInner.md) |  | [optional] |
| **alerts** | [**Array&lt;GetCalendarSecurity200ResponseAlertsInner&gt;**](GetCalendarSecurity200ResponseAlertsInner.md) |  | [optional] |
| **external_sharing** | [**GetCalendarSecurity200ResponseExternalSharing**](GetCalendarSecurity200ResponseExternalSharing.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetCalendarSecurity200Response.new(
  total_calendars: null,
  public_calendars: null,
  private_calendars: null,
  total_members: null,
  delegated_access: null,
  public_calendar_list: null,
  alerts: null,
  external_sharing: null
)
```

