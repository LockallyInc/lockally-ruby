# Lockally::AddOnsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**activate_add_on**](AddOnsApi.md#activate_add_on) | **POST** /v1/add-ons/{name}/activate | Activate an add-on |
| [**cancel_add_on**](AddOnsApi.md#cancel_add_on) | **POST** /v1/add-ons/{name}/cancel | Cancel an add-on |
| [**get_add_on_status**](AddOnsApi.md#get_add_on_status) | **GET** /v1/add-ons/{name} | Get add-on status |
| [**list_add_ons**](AddOnsApi.md#list_add_ons) | **GET** /v1/add-ons | List add-ons |


## activate_add_on

> <ActivateAddOn200Response> activate_add_on(name)

Activate an add-on

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AddOnsApi.new
name = 'name_example' # String | Add-on key

begin
  # Activate an add-on
  result = api_instance.activate_add_on(name)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->activate_add_on: #{e}"
end
```

#### Using the activate_add_on_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ActivateAddOn200Response>, Integer, Hash)> activate_add_on_with_http_info(name)

```ruby
begin
  # Activate an add-on
  data, status_code, headers = api_instance.activate_add_on_with_http_info(name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ActivateAddOn200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->activate_add_on_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | Add-on key |  |

### Return type

[**ActivateAddOn200Response**](ActivateAddOn200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## cancel_add_on

> cancel_add_on(name)

Cancel an add-on

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AddOnsApi.new
name = 'name_example' # String | Add-on key

begin
  # Cancel an add-on
  api_instance.cancel_add_on(name)
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->cancel_add_on: #{e}"
end
```

#### Using the cancel_add_on_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> cancel_add_on_with_http_info(name)

```ruby
begin
  # Cancel an add-on
  data, status_code, headers = api_instance.cancel_add_on_with_http_info(name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->cancel_add_on_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | Add-on key |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## get_add_on_status

> <GetAddOnStatus200Response> get_add_on_status(name)

Get add-on status

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AddOnsApi.new
name = 'name_example' # String | Add-on key

begin
  # Get add-on status
  result = api_instance.get_add_on_status(name)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->get_add_on_status: #{e}"
end
```

#### Using the get_add_on_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAddOnStatus200Response>, Integer, Hash)> get_add_on_status_with_http_info(name)

```ruby
begin
  # Get add-on status
  data, status_code, headers = api_instance.get_add_on_status_with_http_info(name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAddOnStatus200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->get_add_on_status_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | Add-on key |  |

### Return type

[**GetAddOnStatus200Response**](GetAddOnStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_add_ons

> <ListAddOns200Response> list_add_ons

List add-ons

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AddOnsApi.new

begin
  # List add-ons
  result = api_instance.list_add_ons
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->list_add_ons: #{e}"
end
```

#### Using the list_add_ons_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListAddOns200Response>, Integer, Hash)> list_add_ons_with_http_info

```ruby
begin
  # List add-ons
  data, status_code, headers = api_instance.list_add_ons_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListAddOns200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AddOnsApi->list_add_ons_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListAddOns200Response**](ListAddOns200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

