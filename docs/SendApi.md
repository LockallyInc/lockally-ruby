# Lockally::SendApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_messages_get**](SendApi.md#v1_messages_get) | **GET** /v1/messages | List outbound messages |
| [**v1_messages_id_delete**](SendApi.md#v1_messages_id_delete) | **DELETE** /v1/messages/{id} | Cancel a scheduled send |
| [**v1_messages_id_get**](SendApi.md#v1_messages_id_get) | **GET** /v1/messages/{id} | Get message status |
| [**v1_messages_stats_get**](SendApi.md#v1_messages_stats_get) | **GET** /v1/messages/stats | Aggregate delivery stats |
| [**v1_send_batch_post**](SendApi.md#v1_send_batch_post) | **POST** /v1/send/batch | Send a batch of emails |
| [**v1_send_post**](SendApi.md#v1_send_post) | **POST** /v1/send | Send an email |


## v1_messages_get

> <V1MessagesGet200Response> v1_messages_get(opts)

List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. Backs the send-status pill in the SvelteKit /sends view and the outbound search box. 

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
  result = api_instance.v1_messages_get(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_get: #{e}"
end
```

#### Using the v1_messages_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1MessagesGet200Response>, Integer, Hash)> v1_messages_get_with_http_info(opts)

```ruby
begin
  # List outbound messages
  data, status_code, headers = api_instance.v1_messages_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1MessagesGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_get_with_http_info: #{e}"
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

[**V1MessagesGet200Response**](V1MessagesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_messages_id_delete

> v1_messages_id_delete(id)

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
  api_instance.v1_messages_id_delete(id)
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_id_delete: #{e}"
end
```

#### Using the v1_messages_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_messages_id_delete_with_http_info(id)

```ruby
begin
  # Cancel a scheduled send
  data, status_code, headers = api_instance.v1_messages_id_delete_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_id_delete_with_http_info: #{e}"
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


## v1_messages_id_get

> <Message> v1_messages_id_get(id)

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
  result = api_instance.v1_messages_id_get(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_id_get: #{e}"
end
```

#### Using the v1_messages_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Message>, Integer, Hash)> v1_messages_id_get_with_http_info(id)

```ruby
begin
  # Get message status
  data, status_code, headers = api_instance.v1_messages_id_get_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Message>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Message**](Message.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_messages_stats_get

> <MessageStats> v1_messages_stats_get(opts)

Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail — Lockally does no open/click tracking. 

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
  result = api_instance.v1_messages_stats_get(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_stats_get: #{e}"
end
```

#### Using the v1_messages_stats_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MessageStats>, Integer, Hash)> v1_messages_stats_get_with_http_info(opts)

```ruby
begin
  # Aggregate delivery stats
  data, status_code, headers = api_instance.v1_messages_stats_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MessageStats>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_messages_stats_get_with_http_info: #{e}"
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


## v1_send_batch_post

> <V1SendBatchPost200Response> v1_send_batch_post(idempotency_key, v1_send_batch_post_request)

Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently — a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 

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
v1_send_batch_post_request = Lockally::V1SendBatchPostRequest.new({messages: [Lockally::SendMessage.new({from: 'from_example', to: ['to_example']})]}) # V1SendBatchPostRequest | 

begin
  # Send a batch of emails
  result = api_instance.v1_send_batch_post(idempotency_key, v1_send_batch_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_send_batch_post: #{e}"
end
```

#### Using the v1_send_batch_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1SendBatchPost200Response>, Integer, Hash)> v1_send_batch_post_with_http_info(idempotency_key, v1_send_batch_post_request)

```ruby
begin
  # Send a batch of emails
  data, status_code, headers = api_instance.v1_send_batch_post_with_http_info(idempotency_key, v1_send_batch_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1SendBatchPost200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_send_batch_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **idempotency_key** | **String** |  |  |
| **v1_send_batch_post_request** | [**V1SendBatchPostRequest**](V1SendBatchPostRequest.md) |  |  |

### Return type

[**V1SendBatchPost200Response**](V1SendBatchPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_send_post

> <V1SendPost202Response> v1_send_post(idempotency_key, v1_send_post_request)

Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Per design L7 — any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be a non-disabled mailbox owned by the calling tenant on a verified domain. Sending from aliases is not yet supported.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced — 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response — large fan-outs queue noticeably at scale. Hard cap is 100/send. 

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
v1_send_post_request = Lockally::V1SendPostRequest.new({from: 'from_example', to: ['to_example']}) # V1SendPostRequest | 

begin
  # Send an email
  result = api_instance.v1_send_post(idempotency_key, v1_send_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_send_post: #{e}"
end
```

#### Using the v1_send_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1SendPost202Response>, Integer, Hash)> v1_send_post_with_http_info(idempotency_key, v1_send_post_request)

```ruby
begin
  # Send an email
  data, status_code, headers = api_instance.v1_send_post_with_http_info(idempotency_key, v1_send_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1SendPost202Response>
rescue Lockally::ApiError => e
  puts "Error when calling SendApi->v1_send_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **idempotency_key** | **String** |  |  |
| **v1_send_post_request** | [**V1SendPostRequest**](V1SendPostRequest.md) |  |  |

### Return type

[**V1SendPost202Response**](V1SendPost202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

