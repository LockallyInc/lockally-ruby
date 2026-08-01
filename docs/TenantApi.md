# Lockally::TenantApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_tenant_get**](TenantApi.md#v1_tenant_get) | **GET** /v1/tenant | Get the calling tenant |
| [**v1_usage_get**](TenantApi.md#v1_usage_get) | **GET** /v1/usage | Usage snapshot |


## v1_tenant_get

> <Tenant> v1_tenant_get

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
  result = api_instance.v1_tenant_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->v1_tenant_get: #{e}"
end
```

#### Using the v1_tenant_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Tenant>, Integer, Hash)> v1_tenant_get_with_http_info

```ruby
begin
  # Get the calling tenant
  data, status_code, headers = api_instance.v1_tenant_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Tenant>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->v1_tenant_get_with_http_info: #{e}"
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


## v1_usage_get

> <V1UsageGet200Response> v1_usage_get

Usage snapshot

Returns the tenant's current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \"warn when daily quota is 80% used\"). Refreshed live from Postgres — there is no cache, so callers should poll at most once per minute. 

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
  result = api_instance.v1_usage_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->v1_usage_get: #{e}"
end
```

#### Using the v1_usage_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1UsageGet200Response>, Integer, Hash)> v1_usage_get_with_http_info

```ruby
begin
  # Usage snapshot
  data, status_code, headers = api_instance.v1_usage_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1UsageGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->v1_usage_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UsageGet200Response**](V1UsageGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

