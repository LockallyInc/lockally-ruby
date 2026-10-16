# Lockally::SendApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**cancel_message**](SendApi.md#cancel_message) | **DELETE** /v1/messages/{id} | Cancel a scheduled send |
| [**get_message**](SendApi.md#get_message) | **GET** /v1/messages/{id} | Get message status |
| [**get_message_stats**](SendApi.md#get_message_stats) | **GET** /v1/messages/stats | Aggregate delivery stats |
| [**list_messages**](SendApi.md#list_messages) | **GET** /v1/messages | List outbound messages |
| [**send_email**](SendApi.md#send_email) | **POST** /v1/send | Send an email |
| [**send_email_batch**](SendApi.md#send_email_batch) | **POST** /v1/send/batch | Send a batch of emails |


## cancel_message

> cancel_message(id)

Cancel a scheduled send

Cancels a still-scheduled message (future queued_at). Already sending/sent → 409.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Cancel a scheduled send
  api_instance.cancel_message(id)
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->cancel_message: #{e}"
end
```

#### Using the cancel_message_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> cancel_message_with_http_info(id)

```ruby
begin
  # Cancel a scheduled send
  data, status_code, headers = api_instance.cancel_message_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->cancel_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## get_message

> <MessageDetail> get_message(id)

Get message status

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get message status
  result = api_instance.get_message(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->get_message: #{e}"
end
```

#### Using the get_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageDetail>, Integer, Hash)> get_message_with_http_info(id)

```ruby
begin
  # Get message status
  data, status_code, headers = api_instance.get_message_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageDetail>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->get_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**MessageDetail**](MessageDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_message_stats

> <MessageStats> get_message_stats(opts)

Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail, Lockally does no open/click tracking. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
opts = {
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Window start (default 7 days ago).
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Window end (default now).
  domain: 'domain_example' # String | Filter by sender domain.
}

begin
  # Aggregate delivery stats
  result = api_instance.get_message_stats(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->get_message_stats: #{e}"
end
```

#### Using the get_message_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageStats>, Integer, Hash)> get_message_stats_with_http_info(opts)

```ruby
begin
  # Aggregate delivery stats
  data, status_code, headers = api_instance.get_message_stats_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageStats>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->get_message_stats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **Time** | Window start (default 7 days ago). | [optional] |
| **to** | **Time** | Window end (default now). | [optional] |
| **domain** | **String** | Filter by sender domain. | [optional] |

### Return type

[**MessageStats**](MessageStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_messages

> <ListMessages200Response> list_messages(opts)

List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
opts = {
  status: 'queued', # String | 
  sender: 'sender_example', # String | Exact match against the `from` mailbox.
  q: 'q_example', # String | Free-text search across subject + sender.
  since: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Only messages queued at or after this RFC 3339 instant.
  cursor: 'cursor_example', # String | queued_at of the prior page boundary. Pass back the `next_cursor` returned by the previous call.
  limit: 56 # Integer | 
}

begin
  # List outbound messages
  result = api_instance.list_messages(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->list_messages: #{e}"
end
```

#### Using the list_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMessages200Response>, Integer, Hash)> list_messages_with_http_info(opts)

```ruby
begin
  # List outbound messages
  data, status_code, headers = api_instance.list_messages_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMessages200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->list_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **sender** | **String** | Exact match against the &#x60;from&#x60; mailbox. | [optional] |
| **q** | **String** | Free-text search across subject + sender. | [optional] |
| **since** | **Time** | Only messages queued at or after this RFC 3339 instant. | [optional] |
| **cursor** | **String** | queued_at of the prior page boundary. Pass back the &#x60;next_cursor&#x60; returned by the previous call. | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**ListMessages200Response**](ListMessages200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## send_email

> <SendEmail200Response> send_email(idempotency_key, send_email_request)

Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be an address the calling tenant owns on a verified domain. A mailbox always qualifies. On business and combined accounts an **alias** qualifies too, so a send-only address such as `no-reply@` need not be a billed seat. An alias on an unverified domain, or one belonging to another account, is refused with `403`. A catch-all creates no aliases and so grants no sending rights.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced, 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response, large fan-outs queue noticeably at scale. Hard cap is 100/send.  **Not every success is a 202.** Check the status code, not just the body. A `200` means nothing was queued: either every recipient was already suppressed, or the call used a test key and the send was simulated. Both are successes, and neither produces a real delivery. See the `200` response below.  **Warm-up headers.** While the platform is in its outbound warm-up ramp, accepted sends carry `X-Warmup-Day`, `X-Warmup-Daily-Cap` and `X-Warmup-Used-Today`. They describe a platform-wide cap shared by every tenant, not your own allowance, and they disappear once the ramp finishes. Hitting the cap returns 429. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
idempotency_key = 'idempotency_key_example' # String | 
send_email_request = Lockally::SendEmailRequest.new({from: 'from_example', to: ['to_example']}) # SendEmailRequest | 

begin
  # Send an email
  result = api_instance.send_email(idempotency_key, send_email_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->send_email: #{e}"
end
```

#### Using the send_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmail200Response>, Integer, Hash)> send_email_with_http_info(idempotency_key, send_email_request)

```ruby
begin
  # Send an email
  data, status_code, headers = api_instance.send_email_with_http_info(idempotency_key, send_email_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmail200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->send_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **idempotency_key** | **String** |  |  |
| **send_email_request** | [**SendEmailRequest**](SendEmailRequest.md) |  |  |

### Return type

[**SendEmail200Response**](SendEmail200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## send_email_batch

> <SendEmailBatch200Response> send_email_batch(idempotency_key, send_email_batch_request)

Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently, a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SendApi.new
idempotency_key = 'idempotency_key_example' # String | 
send_email_batch_request = Lockally::SendEmailBatchRequest.new({messages: [Lockally::SendMessage.new({from: 'from_example', to: ['to_example']})]}) # SendEmailBatchRequest | 

begin
  # Send a batch of emails
  result = api_instance.send_email_batch(idempotency_key, send_email_batch_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->send_email_batch: #{e}"
end
```

#### Using the send_email_batch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailBatch200Response>, Integer, Hash)> send_email_batch_with_http_info(idempotency_key, send_email_batch_request)

```ruby
begin
  # Send a batch of emails
  data, status_code, headers = api_instance.send_email_batch_with_http_info(idempotency_key, send_email_batch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailBatch200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->send_email_batch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **idempotency_key** | **String** |  |  |
| **send_email_batch_request** | [**SendEmailBatchRequest**](SendEmailBatchRequest.md) |  |  |

### Return type

[**SendEmailBatch200Response**](SendEmailBatch200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

