# Lockally::BillingStatus

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan** | **String** |  |  |
| **display_name** | **String** |  |  |
| **mode** | **String** |  |  |
| **rate_cap_per_min** | **Integer** |  |  |
| **monthly_included_sends** | **Integer** |  |  |
| **msgs_this_period** | **Integer** |  |  |
| **status** | **String** |  |  |
| **price_naira_per_seat** | **Integer** |  |  |
| **subscribed_at** | **Time** |  | [optional] |
| **current_period_end** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **send_units_balance** | **Integer** |  |  |
| **send_units_next_expiry** | **Time** |  | [optional] |
| **unit_bundles** | [**Array&lt;UnitBundle&gt;**](UnitBundle.md) |  |  |
| **catalog** | [**Array&lt;PlanCatalogEntry&gt;**](PlanCatalogEntry.md) |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::BillingStatus.new(
  plan: null,
  display_name: null,
  mode: null,
  rate_cap_per_min: null,
  monthly_included_sends: null,
  msgs_this_period: null,
  status: null,
  price_naira_per_seat: null,
  subscribed_at: null,
  current_period_end: null,
  created_at: null,
  send_units_balance: null,
  send_units_next_expiry: null,
  unit_bundles: null,
  catalog: null
)
```

