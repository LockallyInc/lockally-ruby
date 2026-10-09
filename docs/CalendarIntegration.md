# Lockally::CalendarIntegration

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **provider** | **String** |  |  |
| **label** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **last_sync_at** | **Time** |  | [optional] |
| **error_message** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CalendarIntegration.new(
  id: null,
  tenant_id: null,
  provider: null,
  label: null,
  status: null,
  last_sync_at: null,
  error_message: null,
  created_at: null,
  updated_at: null
)
```

