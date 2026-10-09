# Lockally::AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_ai_config_get**](AiApi.md#v1_ai_config_get) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**v1_ai_config_put**](AiApi.md#v1_ai_config_put) | **PUT** /v1/ai-config | Configure the AI tier |
| [**v1_billing_ai_units_checkout_post**](AiApi.md#v1_billing_ai_units_checkout_post) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**v1_threads_thread_id_classify_post**](AiApi.md#v1_threads_thread_id_classify_post) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |


## v1_ai_config_get

> Object v1_ai_config_get

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
  result = api_instance.v1_ai_config_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_ai_config_get: #{e}"
end
```

#### Using the v1_ai_config_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_ai_config_get_with_http_info

```ruby
begin
  # Read the tenant's AI configuration
  data, status_code, headers = api_instance.v1_ai_config_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_ai_config_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_ai_config_put

> Object v1_ai_config_put

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
  result = api_instance.v1_ai_config_put
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_ai_config_put: #{e}"
end
```

#### Using the v1_ai_config_put_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_ai_config_put_with_http_info

```ruby
begin
  # Configure the AI tier
  data, status_code, headers = api_instance.v1_ai_config_put_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_ai_config_put_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_billing_ai_units_checkout_post

> Object v1_billing_ai_units_checkout_post

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
  result = api_instance.v1_billing_ai_units_checkout_post
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_billing_ai_units_checkout_post: #{e}"
end
```

#### Using the v1_billing_ai_units_checkout_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_billing_ai_units_checkout_post_with_http_info

```ruby
begin
  # Buy prepaid AI units
  data, status_code, headers = api_instance.v1_billing_ai_units_checkout_post_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_billing_ai_units_checkout_post_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_classify_post

> Object v1_threads_thread_id_classify_post(thread_id, opts)

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
  result = api_instance.v1_threads_thread_id_classify_post(thread_id, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_threads_thread_id_classify_post: #{e}"
end
```

#### Using the v1_threads_thread_id_classify_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_classify_post_with_http_info(thread_id, opts)

```ruby
begin
  # LLM-classify a thread
  data, status_code, headers = api_instance.v1_threads_thread_id_classify_post_with_http_info(thread_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AiApi->v1_threads_thread_id_classify_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **refresh** | **Boolean** |  | [optional] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

