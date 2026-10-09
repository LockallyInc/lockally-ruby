# Lockally::WebhooksApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_webhooks_get**](WebhooksApi.md#v1_webhooks_get) | **GET** /v1/webhooks | List webhooks |
| [**v1_webhooks_id_delete**](WebhooksApi.md#v1_webhooks_id_delete) | **DELETE** /v1/webhooks/{id} | Delete a webhook |
| [**v1_webhooks_id_patch**](WebhooksApi.md#v1_webhooks_id_patch) | **PATCH** /v1/webhooks/{id} | Update a webhook |
| [**v1_webhooks_post**](WebhooksApi.md#v1_webhooks_post) | **POST** /v1/webhooks | Create a webhook |


## v1_webhooks_get

> <V1WebhooksGet200Response> v1_webhooks_get

List webhooks

Returns the calling tenant's webhook subscriptions. Never returns the signing secret — only metadata. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::WebhooksApi.new

begin
  # List webhooks
  result = api_instance.v1_webhooks_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_get: #{e}"
end
```

#### Using the v1_webhooks_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1WebhooksGet200Response>, Integer, Hash)> v1_webhooks_get_with_http_info

```ruby
begin
  # List webhooks
  data, status_code, headers = api_instance.v1_webhooks_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1WebhooksGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1WebhooksGet200Response**](V1WebhooksGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_webhooks_id_delete

> v1_webhooks_id_delete(id)

Delete a webhook

Hard-delete; cascades to `webhook_deliveries` history.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::WebhooksApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a webhook
  api_instance.v1_webhooks_id_delete(id)
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_id_delete: #{e}"
end
```

#### Using the v1_webhooks_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_webhooks_id_delete_with_http_info(id)

```ruby
begin
  # Delete a webhook
  data, status_code, headers = api_instance.v1_webhooks_id_delete_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_id_delete_with_http_info: #{e}"
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


## v1_webhooks_id_patch

> <Webhook> v1_webhooks_id_patch(id, v1_webhooks_id_patch_request)

Update a webhook

Supply at least one of `url`, `events`, `paused`. Setting `paused` to `false` ALSO resets `consecutive_failures` to 0 — re-arms the 50-failure auto-pause counter. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::WebhooksApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
v1_webhooks_id_patch_request = Lockally::V1WebhooksIdPatchRequest.new # V1WebhooksIdPatchRequest | 

begin
  # Update a webhook
  result = api_instance.v1_webhooks_id_patch(id, v1_webhooks_id_patch_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_id_patch: #{e}"
end
```

#### Using the v1_webhooks_id_patch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Webhook>, Integer, Hash)> v1_webhooks_id_patch_with_http_info(id, v1_webhooks_id_patch_request)

```ruby
begin
  # Update a webhook
  data, status_code, headers = api_instance.v1_webhooks_id_patch_with_http_info(id, v1_webhooks_id_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Webhook>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_id_patch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **v1_webhooks_id_patch_request** | [**V1WebhooksIdPatchRequest**](V1WebhooksIdPatchRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_webhooks_post

> <Webhook> v1_webhooks_post(v1_webhooks_post_request)

Create a webhook

Subscribes a URL to one or more event types. Returns the `signing_secret` ONCE in the response — store it immediately. The dispatcher signs every outbound POST per design L3:      X-Lockally-Signature: t=<unix>,v1=<hex(hmac_sha256(secret, t + \".\" + body))>  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [internal/webhook](https://github.com/ucheigwedinma/lockally/blob/main/internal/webhook/sign.go).  Event names: see the [event catalogue](https://github.com/ucheigwedinma/lockally/blob/main/docs/v1-design.md#64-webhook-event-catalogue-v1). 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::WebhooksApi.new
v1_webhooks_post_request = Lockally::V1WebhooksPostRequest.new({url: 'https://example.com/webhooks/lockally', events: ['domain.verified']}) # V1WebhooksPostRequest | 

begin
  # Create a webhook
  result = api_instance.v1_webhooks_post(v1_webhooks_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_post: #{e}"
end
```

#### Using the v1_webhooks_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Webhook>, Integer, Hash)> v1_webhooks_post_with_http_info(v1_webhooks_post_request)

```ruby
begin
  # Create a webhook
  data, status_code, headers = api_instance.v1_webhooks_post_with_http_info(v1_webhooks_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Webhook>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->v1_webhooks_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_webhooks_post_request** | [**V1WebhooksPostRequest**](V1WebhooksPostRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

