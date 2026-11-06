# Lockally::TenantHealthReport

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **overall_score** | **Integer** |  |  |
| **checks** | [**Array&lt;TenantHealthCheck&gt;**](TenantHealthCheck.md) |  |  |
| **generated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::TenantHealthReport.new(
  overall_score: null,
  checks: null,
  generated_at: null
)
```

