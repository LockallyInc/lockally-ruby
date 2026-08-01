# Lockally::AliasesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_aliases_address_delete**](AliasesApi.md#v1_aliases_address_delete) | **DELETE** /v1/aliases/{address} | Delete an alias |
| [**v1_aliases_get**](AliasesApi.md#v1_aliases_get) | **GET** /v1/aliases | List aliases |
| [**v1_aliases_post**](AliasesApi.md#v1_aliases_post) | **POST** /v1/aliases | Create an alias |


## v1_aliases_address_delete

> v1_aliases_address_delete(address)

Delete an alias

Hard-delete (no soft-delete window — aliases are cheap to recreate).

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AliasesApi.new
address = 'address_example' # String | 

begin
  # Delete an alias
  api_instance.v1_aliases_address_delete(address)
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_address_delete: #{e}"
end
```

#### Using the v1_aliases_address_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_aliases_address_delete_with_http_info(address)

```ruby
begin
  # Delete an alias
  data, status_code, headers = api_instance.v1_aliases_address_delete_with_http_info(address)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_address_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_aliases_get

> <V1AliasesGet200Response> v1_aliases_get

List aliases

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AliasesApi.new

begin
  # List aliases
  result = api_instance.v1_aliases_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_get: #{e}"
end
```

#### Using the v1_aliases_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1AliasesGet200Response>, Integer, Hash)> v1_aliases_get_with_http_info

```ruby
begin
  # List aliases
  data, status_code, headers = api_instance.v1_aliases_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1AliasesGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1AliasesGet200Response**](V1AliasesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_aliases_post

> <ModelAlias> v1_aliases_post(v1_aliases_post_request)

Create an alias

Creates an email alias. `alias_address` must be on a verified tenant-owned domain. `alias_target` can be any email — intra-tenant or external (forwarding to a Gmail account is a legitimate use). 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AliasesApi.new
v1_aliases_post_request = Lockally::V1AliasesPostRequest.new({alias_address: 'support@acme.com', alias_target: 'alice@acme.com'}) # V1AliasesPostRequest | 

begin
  # Create an alias
  result = api_instance.v1_aliases_post(v1_aliases_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_post: #{e}"
end
```

#### Using the v1_aliases_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ModelAlias>, Integer, Hash)> v1_aliases_post_with_http_info(v1_aliases_post_request)

```ruby
begin
  # Create an alias
  data, status_code, headers = api_instance.v1_aliases_post_with_http_info(v1_aliases_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ModelAlias>
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->v1_aliases_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_aliases_post_request** | [**V1AliasesPostRequest**](V1AliasesPostRequest.md) |  |  |

### Return type

[**ModelAlias**](ModelAlias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

