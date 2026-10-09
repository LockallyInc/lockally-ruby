# Lockally::Tenant

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **slug** | **String** |  |  |
| **display_name** | **String** |  |  |
| **status** | **String** |  |  |
| **plan** | **String** |  |  |
| **rate_cap_per_min** | **Integer** | Per-tenant share of the per-VPS 5/min outbound cap (L6). |  |
| **daily_msg_quota** | **Integer** |  |  |
| **admin_email** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **suspended_at** | **Time** |  | [optional] |
| **closed_at** | **Time** |  | [optional] |
| **hard_delete_after** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Tenant.new(
  id: null,
  slug: workgrid,
  display_name: WorkGrid,
  status: null,
  plan: starter,
  rate_cap_per_min: 1,
  daily_msg_quota: 1000,
  admin_email: null,
  created_at: null,
  suspended_at: null,
  closed_at: null,
  hard_delete_after: null
)
```

