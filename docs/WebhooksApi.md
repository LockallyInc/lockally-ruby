# Lockally::WebhooksApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_webhook**](WebhooksApi.md#create_webhook) | **POST** /v1/webhooks | Create a webhook |
| [**delete_webhook**](WebhooksApi.md#delete_webhook) | **DELETE** /v1/webhooks/{id} | Delete a webhook |
| [**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /v1/webhooks | List webhooks |
| [**update_webhook**](WebhooksApi.md#update_webhook) | **PATCH** /v1/webhooks/{id} | Update a webhook |


## create_webhook

> <Webhook> create_webhook(create_webhook_request)

Create a webhook

Subscribes a URL to one or more event types. Returns the `signing_secret` ONCE in the response, store it immediately. Every outbound POST is signed:      X-Lockally-Signature: t=<unix>,v1=<hex(hmac_sha256(secret, t + \".\" + body))>  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [Signature verification](https://developers.lockally.com/webhooks/verification/).  Event names: see the [event catalogue](https://developers.lockally.com/webhooks/events/). 

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
create_webhook_request = Lockally::CreateWebhookRequest.new({url: 'https://example.com/webhooks/lockally', events: ['domain.verified']}) # CreateWebhookRequest | 

begin
  # Create a webhook
  result = api_instance.create_webhook(create_webhook_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->create_webhook: #{e}"
end
```

#### Using the create_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Webhook>, Integer, Hash)> create_webhook_with_http_info(create_webhook_request)

```ruby
begin
  # Create a webhook
  data, status_code, headers = api_instance.create_webhook_with_http_info(create_webhook_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Webhook>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->create_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_webhook_request** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_webhook

> delete_webhook(id)

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
  api_instance.delete_webhook(id)
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->delete_webhook: #{e}"
end
```

#### Using the delete_webhook_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_webhook_with_http_info(id)

```ruby
begin
  # Delete a webhook
  data, status_code, headers = api_instance.delete_webhook_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->delete_webhook_with_http_info: #{e}"
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


## list_webhooks

> <ListWebhooks200Response> list_webhooks

List webhooks

Returns the calling tenant's webhook subscriptions. Never returns the signing secret, only metadata. 

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
  result = api_instance.list_webhooks
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks: #{e}"
end
```

#### Using the list_webhooks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListWebhooks200Response>, Integer, Hash)> list_webhooks_with_http_info

```ruby
begin
  # List webhooks
  data, status_code, headers = api_instance.list_webhooks_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListWebhooks200Response>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_webhook

> <Webhook> update_webhook(id, update_webhook_request)

Update a webhook

Supply at least one of `url`, `events`, `paused`. Setting `paused` to `false` ALSO resets `consecutive_failures` to 0, re-arms the 50-failure auto-pause counter. 

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
update_webhook_request = Lockally::UpdateWebhookRequest.new # UpdateWebhookRequest | 

begin
  # Update a webhook
  result = api_instance.update_webhook(id, update_webhook_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->update_webhook: #{e}"
end
```

#### Using the update_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Webhook>, Integer, Hash)> update_webhook_with_http_info(id, update_webhook_request)

```ruby
begin
  # Update a webhook
  data, status_code, headers = api_instance.update_webhook_with_http_info(id, update_webhook_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Webhook>
rescue Lockally::ApiError => e
  puts "Error when calling WebhooksApi->update_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_webhook_request** | [**UpdateWebhookRequest**](UpdateWebhookRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

