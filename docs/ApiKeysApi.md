# Lockally::ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_api_key**](ApiKeysApi.md#create_api_key) | **POST** /v1/api-keys | Create an API key |
| [**list_api_keys**](ApiKeysApi.md#list_api_keys) | **GET** /v1/api-keys | List API keys |
| [**revoke_api_key**](ApiKeysApi.md#revoke_api_key) | **DELETE** /v1/api-keys/{id} | Revoke an API key |


## create_api_key

> <CreateApiKey201Response> create_api_key(create_api_key_request)

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
create_api_key_request = Lockally::CreateApiKeyRequest.new({label: 'ci-pipeline', scopes: ['tenant:read']}) # CreateApiKeyRequest | 

begin
  # Create an API key
  result = api_instance.create_api_key(create_api_key_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->create_api_key: #{e}"
end
```

#### Using the create_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateApiKey201Response>, Integer, Hash)> create_api_key_with_http_info(create_api_key_request)

```ruby
begin
  # Create an API key
  data, status_code, headers = api_instance.create_api_key_with_http_info(create_api_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateApiKey201Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->create_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_api_key_request** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md) |  |  |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## list_api_keys

> <ListApiKeys200Response> list_api_keys

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
  result = api_instance.list_api_keys
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->list_api_keys: #{e}"
end
```

#### Using the list_api_keys_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListApiKeys200Response>, Integer, Hash)> list_api_keys_with_http_info

```ruby
begin
  # List API keys
  data, status_code, headers = api_instance.list_api_keys_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListApiKeys200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->list_api_keys_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## revoke_api_key

> revoke_api_key(id)

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
  api_instance.revoke_api_key(id)
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->revoke_api_key: #{e}"
end
```

#### Using the revoke_api_key_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_api_key_with_http_info(id)

```ruby
begin
  # Revoke an API key
  data, status_code, headers = api_instance.revoke_api_key_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->revoke_api_key_with_http_info: #{e}"
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

