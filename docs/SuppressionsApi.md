# Lockally::SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_suppressions_email_delete**](SuppressionsApi.md#v1_suppressions_email_delete) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**v1_suppressions_email_get**](SuppressionsApi.md#v1_suppressions_email_get) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**v1_suppressions_get**](SuppressionsApi.md#v1_suppressions_get) | **GET** /v1/suppressions | List suppressed recipients |
| [**v1_suppressions_post**](SuppressionsApi.md#v1_suppressions_post) | **POST** /v1/suppressions | Add a suppression |


## v1_suppressions_email_delete

> v1_suppressions_email_delete(email)

Remove a suppression

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SuppressionsApi.new
email = 'email_example' # String | 

begin
  # Remove a suppression
  api_instance.v1_suppressions_email_delete(email)
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_email_delete: #{e}"
end
```

#### Using the v1_suppressions_email_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_suppressions_email_delete_with_http_info(email)

```ruby
begin
  # Remove a suppression
  data, status_code, headers = api_instance.v1_suppressions_email_delete_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_email_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_suppressions_email_get

> <Suppression> v1_suppressions_email_get(email)

Check whether an address is suppressed

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SuppressionsApi.new
email = 'email_example' # String | 

begin
  # Check whether an address is suppressed
  result = api_instance.v1_suppressions_email_get(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_email_get: #{e}"
end
```

#### Using the v1_suppressions_email_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Suppression>, Integer, Hash)> v1_suppressions_email_get_with_http_info(email)

```ruby
begin
  # Check whether an address is suppressed
  data, status_code, headers = api_instance.v1_suppressions_email_get_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Suppression>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_email_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_suppressions_get

> <V1SuppressionsGet200Response> v1_suppressions_get(opts)

List suppressed recipients

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SuppressionsApi.new
opts = {
  reason: 'unsubscribe', # String | 
  cursor: 'cursor_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List suppressed recipients
  result = api_instance.v1_suppressions_get(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_get: #{e}"
end
```

#### Using the v1_suppressions_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1SuppressionsGet200Response>, Integer, Hash)> v1_suppressions_get_with_http_info(opts)

```ruby
begin
  # List suppressed recipients
  data, status_code, headers = api_instance.v1_suppressions_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1SuppressionsGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **reason** | **String** |  | [optional] |
| **cursor** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**V1SuppressionsGet200Response**](V1SuppressionsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_suppressions_post

> <Suppression> v1_suppressions_post(v1_suppressions_post_request)

Add a suppression

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::SuppressionsApi.new
v1_suppressions_post_request = Lockally::V1SuppressionsPostRequest.new({email: 'email_example'}) # V1SuppressionsPostRequest | 

begin
  # Add a suppression
  result = api_instance.v1_suppressions_post(v1_suppressions_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_post: #{e}"
end
```

#### Using the v1_suppressions_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Suppression>, Integer, Hash)> v1_suppressions_post_with_http_info(v1_suppressions_post_request)

```ruby
begin
  # Add a suppression
  data, status_code, headers = api_instance.v1_suppressions_post_with_http_info(v1_suppressions_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Suppression>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->v1_suppressions_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_suppressions_post_request** | [**V1SuppressionsPostRequest**](V1SuppressionsPostRequest.md) |  |  |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

