# Lockally::AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**classify_thread**](AiApi.md#classify_thread) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |
| [**create_ai_units_checkout**](AiApi.md#create_ai_units_checkout) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**get_ai_config**](AiApi.md#get_ai_config) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**update_ai_config**](AiApi.md#update_ai_config) | **PUT** /v1/ai-config | Configure the AI tier |


## classify_thread

> <ThreadClassification> classify_thread(thread_id, opts)

LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant's AI tier (BYOK or prepaid units — see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh=true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AiApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
opts = {
  refresh: true # Boolean | 
}

begin
  # LLM-classify a thread
  result = api_instance.classify_thread(thread_id, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->classify_thread: #{e}"
end
```

#### Using the classify_thread_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ThreadClassification>, Integer, Hash)> classify_thread_with_http_info(thread_id, opts)

```ruby
begin
  # LLM-classify a thread
  data, status_code, headers = api_instance.classify_thread_with_http_info(thread_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ThreadClassification>
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->classify_thread_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **refresh** | **Boolean** |  | [optional] |

### Return type

[**ThreadClassification**](ThreadClassification.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_ai_units_checkout

> <CreateAiUnitsCheckout200Response> create_ai_units_checkout

Buy prepaid AI units

Body: {\"bundle\": \"100|500|2000\"}. One classification = one unit; bundles expire after 6 months. Admin session required. 503 until Paystack billing is configured.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AiApi.new

begin
  # Buy prepaid AI units
  result = api_instance.create_ai_units_checkout
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->create_ai_units_checkout: #{e}"
end
```

#### Using the create_ai_units_checkout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateAiUnitsCheckout200Response>, Integer, Hash)> create_ai_units_checkout_with_http_info

```ruby
begin
  # Buy prepaid AI units
  data, status_code, headers = api_instance.create_ai_units_checkout_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateAiUnitsCheckout200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->create_ai_units_checkout_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CreateAiUnitsCheckout200Response**](CreateAiUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_ai_config

> <AiConfig> get_ai_config

Read the tenant's AI configuration

Mode (off/byok/units), model, masked key hint, AI-unit balance, whether the units tier is available on this deployment.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AiApi.new

begin
  # Read the tenant's AI configuration
  result = api_instance.get_ai_config
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->get_ai_config: #{e}"
end
```

#### Using the get_ai_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AiConfig>, Integer, Hash)> get_ai_config_with_http_info

```ruby
begin
  # Read the tenant's AI configuration
  data, status_code, headers = api_instance.get_ai_config_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AiConfig>
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->get_ai_config_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AiConfig**](AiConfig.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_ai_config

> <AiConfigUpdate> update_ai_config

Configure the AI tier

Body: {\"mode\": \"off|byok|units\", \"model\": \"...\", \"anthropic_key\": \"sk-ant-...\"}. BYOK keys are stored AES-256-GCM encrypted; the cleartext is never returned. Omit anthropic_key to keep the stored one.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AiApi.new

begin
  # Configure the AI tier
  result = api_instance.update_ai_config
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->update_ai_config: #{e}"
end
```

#### Using the update_ai_config_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AiConfigUpdate>, Integer, Hash)> update_ai_config_with_http_info

```ruby
begin
  # Configure the AI tier
  data, status_code, headers = api_instance.update_ai_config_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AiConfigUpdate>
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->update_ai_config_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AiConfigUpdate**](AiConfigUpdate.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

