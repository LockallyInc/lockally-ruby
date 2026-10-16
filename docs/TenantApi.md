# Lockally::TenantApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_tenant**](TenantApi.md#get_tenant) | **GET** /v1/tenant | Get the calling tenant |
| [**get_usage**](TenantApi.md#get_usage) | **GET** /v1/usage | Usage snapshot |


## get_tenant

> <Tenant> get_tenant

Get the calling tenant

Returns the tenant the presented API key belongs to.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TenantApi.new

begin
  # Get the calling tenant
  result = api_instance.get_tenant
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_tenant: #{e}"
end
```

#### Using the get_tenant_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Tenant>, Integer, Hash)> get_tenant_with_http_info

```ruby
begin
  # Get the calling tenant
  data, status_code, headers = api_instance.get_tenant_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Tenant>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_tenant_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Tenant**](Tenant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_usage

> <GetUsage200Response> get_usage

Usage snapshot

Returns the tenant's current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \"warn when daily quota is 80% used\"). Computed live on request, so there is no cache, so callers should poll at most once per minute. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TenantApi.new

begin
  # Usage snapshot
  result = api_instance.get_usage
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_usage: #{e}"
end
```

#### Using the get_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUsage200Response>, Integer, Hash)> get_usage_with_http_info

```ruby
begin
  # Usage snapshot
  data, status_code, headers = api_instance.get_usage_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUsage200Response>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_usage_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetUsage200Response**](GetUsage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

