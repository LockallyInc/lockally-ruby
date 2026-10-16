# Lockally::AliasesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_alias**](AliasesApi.md#create_alias) | **POST** /v1/aliases | Create an alias |
| [**delete_alias**](AliasesApi.md#delete_alias) | **DELETE** /v1/aliases/{address} | Delete an alias |
| [**list_aliases**](AliasesApi.md#list_aliases) | **GET** /v1/aliases | List aliases |


## create_alias

> <ModelAlias> create_alias(create_alias_request)

Create an alias

Creates an email alias. `alias_address` must be on a verified tenant-owned domain and must not be the address of an existing mailbox (live, suspended or deleted). `alias_target` must be an active mailbox in the same workspace; forwarding to an address Lockally does not host is not supported. The alias delivers as soon as the call returns. 

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
create_alias_request = Lockally::CreateAliasRequest.new({alias_address: 'support@acme.com', alias_target: 'alice@acme.com'}) # CreateAliasRequest | 

begin
  # Create an alias
  result = api_instance.create_alias(create_alias_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->create_alias: #{e}"
end
```

#### Using the create_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ModelAlias>, Integer, Hash)> create_alias_with_http_info(create_alias_request)

```ruby
begin
  # Create an alias
  data, status_code, headers = api_instance.create_alias_with_http_info(create_alias_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ModelAlias>
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->create_alias_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_alias_request** | [**CreateAliasRequest**](CreateAliasRequest.md) |  |  |

### Return type

[**ModelAlias**](ModelAlias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_alias

> delete_alias(address)

Delete an alias

Hard-delete (no soft-delete window, aliases are cheap to recreate).

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
  api_instance.delete_alias(address)
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->delete_alias: #{e}"
end
```

#### Using the delete_alias_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_alias_with_http_info(address)

```ruby
begin
  # Delete an alias
  data, status_code, headers = api_instance.delete_alias_with_http_info(address)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->delete_alias_with_http_info: #{e}"
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


## list_aliases

> <ListAliases200Response> list_aliases

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
  result = api_instance.list_aliases
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->list_aliases: #{e}"
end
```

#### Using the list_aliases_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListAliases200Response>, Integer, Hash)> list_aliases_with_http_info

```ruby
begin
  # List aliases
  data, status_code, headers = api_instance.list_aliases_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListAliases200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AliasesApi->list_aliases_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListAliases200Response**](ListAliases200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

