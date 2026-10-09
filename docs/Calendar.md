# Lockally::Calendar

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **name** | **String** |  |  |
| **color** | **String** |  | [optional] |
| **owner_email** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **calendar_type** | **String** | What the calendar is for. Separate from visibility, which is who may see it: a team calendar can be open to everyone and a department one restricted to named people. \&quot;personal\&quot; is a person&#39;s own and is not listed in the console&#39;s management table.  | [optional] |
| **owner_unit** | **String** | The owning department or office. Empty on a personal calendar, which is owned by owner_email. | [optional] |
| **visibility** | **String** |  |  |
| **access_department** | **String** | Which department may see it, when visibility is \&quot;department\&quot;. Matched against the department recorded on a user, so access follows a person between departments with no membership list to maintain.  | [optional] |
| **status** | **String** | Archived keeps the calendar, its events and its feed, and stops it taking new events. | [optional] |
| **feed_url** | **String** |  | [optional] |
| **event_count** | **Integer** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Calendar.new(
  id: null,
  tenant_id: null,
  name: null,
  color: null,
  owner_email: null,
  description: null,
  calendar_type: null,
  owner_unit: null,
  visibility: null,
  access_department: null,
  status: null,
  feed_url: null,
  event_count: null,
  created_at: null,
  updated_at: null
)
```

