# Lockally::V1UsageGet200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailboxes_active** | **Integer** | Mailboxes that are neither disabled nor soft-deleted. |  |
| **mailboxes_total** | **Integer** | All mailboxes for this tenant, including disabled/soft-deleted. | [optional] |
| **domains_verified** | **Integer** | Domains that have passed DNS verification. | [optional] |
| **domains_total** | **Integer** |  | [optional] |
| **messages_sent_last_60s** | **Integer** | Sends in the 60-second window ending now. Used by the rate-cap check. | [optional] |
| **messages_sent_today_utc** | **Integer** | Sends since 00:00 UTC. Compared against &#x60;daily_msg_quota&#x60;. | [optional] |
| **messages_sent_last_30d** | **Integer** | Rolling 30-day send count (not calendar month). | [optional] |
| **bytes_stored** | **Integer** | Lifetime sum of &#x60;messages.size_bytes&#x60; for this tenant. | [optional] |
| **rate_cap_per_min** | **Integer** | Per-tenant outbound rate cap (sends per minute). | [optional] |
| **daily_msg_quota** | **Integer** | Per-tenant daily send quota (UTC day boundary). | [optional] |
| **webhooks_total** | **Integer** |  | [optional] |
| **webhooks_paused** | **Integer** | Webhook subscriptions auto-paused after 50 consecutive failures (LT2). | [optional] |
| **generated_at** | **Time** | When this snapshot was generated, RFC 3339 UTC. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::V1UsageGet200Response.new(
  mailboxes_active: null,
  mailboxes_total: null,
  domains_verified: null,
  domains_total: null,
  messages_sent_last_60s: null,
  messages_sent_today_utc: null,
  messages_sent_last_30d: null,
  bytes_stored: null,
  rate_cap_per_min: null,
  daily_msg_quota: null,
  webhooks_total: null,
  webhooks_paused: null,
  generated_at: null
)
```

