# Lockally::Webhook

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **url** | **String** |  |  |
| **events** | **Array&lt;String&gt;** |  |  |
| **paused** | **Boolean** |  |  |
| **paused_at** | **Time** |  | [optional] |
| **last_success_at** | **Time** |  | [optional] |
| **last_failure_at** | **Time** |  | [optional] |
| **consecutive_failures** | **Integer** |  |  |
| **created_at** | **Time** |  |  |
| **signing_secret** | **String** | Hex-encoded HMAC-SHA256 key. Present ONLY on POST response. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Webhook.new(
  id: null,
  tenant_id: null,
  url: null,
  events: null,
  paused: null,
  paused_at: null,
  last_success_at: null,
  last_failure_at: null,
  consecutive_failures: null,
  created_at: null,
  signing_secret: null
)
```

