# Lockally::ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_api_key**](ApiKeysApi.md#create_api_key) | **POST** /v1/api-keys | Create an API key |
| [**list_api_keys**](ApiKeysApi.md#list_api_keys) | **GET** /v1/api-keys | List API keys |
| [**revoke_api_key**](ApiKeysApi.md#revoke_api_key) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**rotate_api_key**](ApiKeysApi.md#rotate_api_key) | **POST** /v1/api-keys/{id}/rotate | Rotate an API key |
| [**update_api_key**](ApiKeysApi.md#update_api_key) | **PATCH** /v1/api-keys/{id} | Update an API key |


## create_api_key

> <CreateApiKey201Response> create_api_key(create_api_key_request)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY**, store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 

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

> <ListApiKeys200Response> list_api_keys(opts)

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned, only prefix + metadata. 

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
opts = {
  sort: 'label', # String | Field to order by. This list holds tens of rows per account, so every column is offered and none needs an index.
  order: 'asc' # String | Defaults to desc for the default field and asc for any other. Always tie-broken on id, so the order is total.
}

begin
  # List API keys
  result = api_instance.list_api_keys(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->list_api_keys: #{e}"
end
```

#### Using the list_api_keys_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListApiKeys200Response>, Integer, Hash)> list_api_keys_with_http_info(opts)

```ruby
begin
  # List API keys
  data, status_code, headers = api_instance.list_api_keys_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListApiKeys200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->list_api_keys_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sort** | **String** | Field to order by. This list holds tens of rows per account, so every column is offered and none needs an index. | [optional][default to &#39;created_at&#39;] |
| **order** | **String** | Defaults to desc for the default field and asc for any other. Always tie-broken on id, so the order is total. | [optional] |

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

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call, that would lock you out. Use a different `tenant:admin` key. 

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


## rotate_api_key

> <CreateApiKey201Response> rotate_api_key(id, opts)

Rotate an API key

Issues a successor key and puts a short expiry on this one, so **both work until the overlap ends**. That window is the point: without it, rotation is revocation with extra steps and every caller has to swap credentials in the same instant.  The successor inherits this key's scopes, its label (the label names the integration, and the integration has not changed) and its test flag. Its full `secret` is in this response and nowhere else.  The response's `expires_at` is the **predecessor's** deadline, so you can see from the rotation itself how long you have to cut over.  A key that has already been rotated cannot be rotated again: chaining overlaps would leave several live keys for one integration, which is the opposite of the intent. Rotate the successor instead. 

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
opts = {
  rotate_api_key_request: Lockally::RotateApiKeyRequest.new # RotateApiKeyRequest | 
}

begin
  # Rotate an API key
  result = api_instance.rotate_api_key(id, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->rotate_api_key: #{e}"
end
```

#### Using the rotate_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateApiKey201Response>, Integer, Hash)> rotate_api_key_with_http_info(id, opts)

```ruby
begin
  # Rotate an API key
  data, status_code, headers = api_instance.rotate_api_key_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateApiKey201Response>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->rotate_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **rotate_api_key_request** | [**RotateApiKeyRequest**](RotateApiKeyRequest.md) |  | [optional] |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_api_key

> <APIKey> update_api_key(id, update_api_key_request)

Update an API key

Changes a key's label, scopes or expiry in place, without reissuing the secret.  **Every field is optional and absent means unchanged.** Renaming a key does not clear its expiry. For `expires_at` there are three distinct requests: omit the field to leave the expiry alone, send a timestamp to set one, and send an explicit `null` to remove one.  Scopes are replaced wholesale, not merged. This endpoint does not restrict which scopes you may grant, because `POST /v1/api-keys` never has either: a key with `tenant:admin` can already mint a key with any scope, so `tenant:admin` is root-equivalent for key management.  A revoked key cannot be updated. 

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
update_api_key_request = Lockally::UpdateApiKeyRequest.new # UpdateApiKeyRequest | 

begin
  # Update an API key
  result = api_instance.update_api_key(id, update_api_key_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->update_api_key: #{e}"
end
```

#### Using the update_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<APIKey>, Integer, Hash)> update_api_key_with_http_info(id, update_api_key_request)

```ruby
begin
  # Update an API key
  data, status_code, headers = api_instance.update_api_key_with_http_info(id, update_api_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <APIKey>
rescue Lockally::ApiError => e
  puts "Error when calling ApiKeysApi->update_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_api_key_request** | [**UpdateApiKeyRequest**](UpdateApiKeyRequest.md) |  |  |

### Return type

[**APIKey**](APIKey.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

