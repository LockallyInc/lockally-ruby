# Lockally::BillingApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_billing_checkout**](BillingApi.md#create_billing_checkout) | **POST** /v1/billing/checkout | Create a plan checkout session |
| [**create_units_checkout**](BillingApi.md#create_units_checkout) | **POST** /v1/billing/units/checkout | Create a send-units checkout session |
| [**get_billing**](BillingApi.md#get_billing) | **GET** /v1/billing | Get billing status |


## create_billing_checkout

> <CreateBillingCheckout200Response> create_billing_checkout(create_billing_checkout_request)

Create a plan checkout session

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::BillingApi.new
create_billing_checkout_request = Lockally::CreateBillingCheckoutRequest.new({plan: 'free'}) # CreateBillingCheckoutRequest | 

begin
  # Create a plan checkout session
  result = api_instance.create_billing_checkout(create_billing_checkout_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->create_billing_checkout: #{e}"
end
```

#### Using the create_billing_checkout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateBillingCheckout200Response>, Integer, Hash)> create_billing_checkout_with_http_info(create_billing_checkout_request)

```ruby
begin
  # Create a plan checkout session
  data, status_code, headers = api_instance.create_billing_checkout_with_http_info(create_billing_checkout_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateBillingCheckout200Response>
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->create_billing_checkout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_billing_checkout_request** | [**CreateBillingCheckoutRequest**](CreateBillingCheckoutRequest.md) |  |  |

### Return type

[**CreateBillingCheckout200Response**](CreateBillingCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_units_checkout

> <CreateUnitsCheckout200Response> create_units_checkout(create_units_checkout_request)

Create a send-units checkout session

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::BillingApi.new
create_units_checkout_request = Lockally::CreateUnitsCheckoutRequest.new({bundle: '1k'}) # CreateUnitsCheckoutRequest | 

begin
  # Create a send-units checkout session
  result = api_instance.create_units_checkout(create_units_checkout_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->create_units_checkout: #{e}"
end
```

#### Using the create_units_checkout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateUnitsCheckout200Response>, Integer, Hash)> create_units_checkout_with_http_info(create_units_checkout_request)

```ruby
begin
  # Create a send-units checkout session
  data, status_code, headers = api_instance.create_units_checkout_with_http_info(create_units_checkout_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateUnitsCheckout200Response>
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->create_units_checkout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_units_checkout_request** | [**CreateUnitsCheckoutRequest**](CreateUnitsCheckoutRequest.md) |  |  |

### Return type

[**CreateUnitsCheckout200Response**](CreateUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## get_billing

> <BillingStatus> get_billing

Get billing status

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::BillingApi.new

begin
  # Get billing status
  result = api_instance.get_billing
  p result
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->get_billing: #{e}"
end
```

#### Using the get_billing_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BillingStatus>, Integer, Hash)> get_billing_with_http_info

```ruby
begin
  # Get billing status
  data, status_code, headers = api_instance.get_billing_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BillingStatus>
rescue Lockally::ApiError => e
  puts "Error when calling BillingApi->get_billing_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**BillingStatus**](BillingStatus.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

