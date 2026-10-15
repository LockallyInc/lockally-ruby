# Lockally::GetIntegrationsSummary200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_requests_today** | **Integer** |  | [optional] |
| **active_api_keys** | **Integer** |  | [optional] |
| **api_keys** | [**Array&lt;GetIntegrationsSummary200ResponseApiKeysInner&gt;**](GetIntegrationsSummary200ResponseApiKeysInner.md) |  | [optional] |
| **webhook_failures** | **Integer** |  | [optional] |
| **webhooks_total** | **Integer** |  | [optional] |
| **webhooks** | [**Array&lt;GetIntegrationsSummary200ResponseWebhooksInner&gt;**](GetIntegrationsSummary200ResponseWebhooksInner.md) |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetIntegrationsSummary200Response.new(
  api_requests_today: null,
  active_api_keys: null,
  api_keys: null,
  webhook_failures: null,
  webhooks_total: null,
  webhooks: null,
  generated_at: null
)
```

