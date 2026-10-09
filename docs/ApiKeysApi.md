# Lockally::ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_api_keys_get**](ApiKeysApi.md#v1_api_keys_get) | **GET** /v1/api-keys | List API keys |
| [**v1_api_keys_id_delete**](ApiKeysApi.md#v1_api_keys_id_delete) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**v1_api_keys_post**](ApiKeysApi.md#v1_api_keys_post) | **POST** /v1/api-keys | Create an API key |


## v1_api_keys_get

> <V1ApiKeysGet200Response> v1_api_keys_get

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned — only prefix + metadata. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ApiKeysApi.new

begin
  # List API keys
  result = api_instance.v1_api_keys_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_get: #{e}"
end
```

#### Using the v1_api_keys_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1ApiKeysGet200Response>, Integer, Hash)> v1_api_keys_get_with_http_info

```ruby
begin
  # List API keys
  data, status_code, headers = api_instance.v1_api_keys_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1ApiKeysGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1ApiKeysGet200Response**](V1ApiKeysGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_api_keys_id_delete

> v1_api_keys_id_delete(id)

Revoke an API key

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call — that would lock you out. Use a different `tenant:admin` key. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ApiKeysApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Revoke an API key
  api_instance.v1_api_keys_id_delete(id)
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_id_delete: #{e}"
end
```

#### Using the v1_api_keys_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_api_keys_id_delete_with_http_info(id)

```ruby
begin
  # Revoke an API key
  data, status_code, headers = api_instance.v1_api_keys_id_delete_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_id_delete_with_http_info: #{e}"
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


## v1_api_keys_post

> <V1ApiKeysPost201Response> v1_api_keys_post(v1_api_keys_post_request)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY** — store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ApiKeysApi.new
v1_api_keys_post_request = Lockally::V1ApiKeysPostRequest.new({label: 'ci-pipeline', scopes: ['tenant:read']}) # V1ApiKeysPostRequest | 

begin
  # Create an API key
  result = api_instance.v1_api_keys_post(v1_api_keys_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_post: #{e}"
end
```

#### Using the v1_api_keys_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1ApiKeysPost201Response>, Integer, Hash)> v1_api_keys_post_with_http_info(v1_api_keys_post_request)

```ruby
begin
  # Create an API key
  data, status_code, headers = api_instance.v1_api_keys_post_with_http_info(v1_api_keys_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1ApiKeysPost201Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->v1_api_keys_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_api_keys_post_request** | [**V1ApiKeysPostRequest**](V1ApiKeysPostRequest.md) |  |  |

### Return type

[**V1ApiKeysPost201Response**](V1ApiKeysPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

