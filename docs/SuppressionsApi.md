# Lockally::SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_suppression**](SuppressionsApi.md#create_suppression) | **POST** /v1/suppressions | Add a suppression |
| [**delete_suppression**](SuppressionsApi.md#delete_suppression) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**get_suppression**](SuppressionsApi.md#get_suppression) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**list_suppressions**](SuppressionsApi.md#list_suppressions) | **GET** /v1/suppressions | List suppressed recipients |


## create_suppression

> <Suppression> create_suppression(create_suppression_request)

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
create_suppression_request = Lockally::CreateSuppressionRequest.new({email: 'email_example'}) # CreateSuppressionRequest | 

begin
  # Add a suppression
  result = api_instance.create_suppression(create_suppression_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->create_suppression: #{e}"
end
```

#### Using the create_suppression_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Suppression>, Integer, Hash)> create_suppression_with_http_info(create_suppression_request)

```ruby
begin
  # Add a suppression
  data, status_code, headers = api_instance.create_suppression_with_http_info(create_suppression_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Suppression>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->create_suppression_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_suppression_request** | [**CreateSuppressionRequest**](CreateSuppressionRequest.md) |  |  |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_suppression

> delete_suppression(email)

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
  api_instance.delete_suppression(email)
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->delete_suppression: #{e}"
end
```

#### Using the delete_suppression_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_suppression_with_http_info(email)

```ruby
begin
  # Remove a suppression
  data, status_code, headers = api_instance.delete_suppression_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->delete_suppression_with_http_info: #{e}"
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


## get_suppression

> <Suppression> get_suppression(email)

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
  result = api_instance.get_suppression(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->get_suppression: #{e}"
end
```

#### Using the get_suppression_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Suppression>, Integer, Hash)> get_suppression_with_http_info(email)

```ruby
begin
  # Check whether an address is suppressed
  data, status_code, headers = api_instance.get_suppression_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Suppression>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->get_suppression_with_http_info: #{e}"
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


## list_suppressions

> <ListSuppressions200Response> list_suppressions(opts)

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
  result = api_instance.list_suppressions(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->list_suppressions: #{e}"
end
```

#### Using the list_suppressions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListSuppressions200Response>, Integer, Hash)> list_suppressions_with_http_info(opts)

```ruby
begin
  # List suppressed recipients
  data, status_code, headers = api_instance.list_suppressions_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListSuppressions200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SuppressionsApi->list_suppressions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **reason** | **String** |  | [optional] |
| **cursor** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**ListSuppressions200Response**](ListSuppressions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

