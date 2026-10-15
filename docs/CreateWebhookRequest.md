# Lockally::CreateWebhookRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url** | **String** | HTTPS recommended (HTTP allowed for local development). |  |
| **events** | **Array&lt;String&gt;** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateWebhookRequest.new(
  url: https://example.com/webhooks/lockally,
  events: null
)
```

