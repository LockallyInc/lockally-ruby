# Lockally::PlanCatalogEntry

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **display_name** | **String** |  |  |
| **description** | **String** |  |  |
| **price_naira_per_seat** | **Integer** |  |  |
| **rate_cap_per_min** | **Integer** |  |  |
| **monthly_included_sends** | **Integer** |  |  |
| **has_shared_mailboxes** | **Boolean** |  |  |
| **has_send_units** | **Boolean** |  |  |
| **has_ai_units** | **Boolean** |  |  |
| **has_e2e_encryption** | **Boolean** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::PlanCatalogEntry.new(
  name: null,
  display_name: null,
  description: null,
  price_naira_per_seat: null,
  rate_cap_per_min: null,
  monthly_included_sends: null,
  has_shared_mailboxes: null,
  has_send_units: null,
  has_ai_units: null,
  has_e2e_encryption: null
)
```

