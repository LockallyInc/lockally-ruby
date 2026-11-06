# Lockally::TenantApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_tenant**](TenantApi.md#get_tenant) | **GET** /v1/tenant | Get the calling tenant |
| [**get_tracking_policy**](TenantApi.md#get_tracking_policy) | **GET** /v1/tracking | Get the engagement tracking policy |
| [**get_usage**](TenantApi.md#get_usage) | **GET** /v1/usage | Usage snapshot |
| [**update_tracking_policy**](TenantApi.md#update_tracking_policy) | **PUT** /v1/tracking | Update the engagement tracking policy |


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


## get_tracking_policy

> <TrackingPolicy> get_tracking_policy

Get the engagement tracking policy

Whether open and click tracking are enabled for this account. **Both are off until switched on**, and an account that has never set a policy reads as off rather than as an error.  `configured` reports whether this deployment holds a signing secret. Without one no tracking token can be minted or verified, so tracking cannot work however the flags are set, and a caller seeing `track_opens: true` with nothing arriving deserves to know why. 

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
  # Get the engagement tracking policy
  result = api_instance.get_tracking_policy
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_tracking_policy: #{e}"
end
```

#### Using the get_tracking_policy_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TrackingPolicy>, Integer, Hash)> get_tracking_policy_with_http_info

```ruby
begin
  # Get the engagement tracking policy
  data, status_code, headers = api_instance.get_tracking_policy_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TrackingPolicy>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->get_tracking_policy_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**TrackingPolicy**](TrackingPolicy.md)

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


## update_tracking_policy

> <TrackingPolicy> update_tracking_policy(update_tracking_policy_request)

Update the engagement tracking policy

Enables or disables tracking for the account. Send either flag or both; an omitted flag is left unchanged rather than reset.  **Enabling this changes what Lockally collects about your recipients**, who have no relationship with us. You are the controller for them. What is collected is a user-agent string, a timestamp, and for a click the destination URL: **no IP address**, ever. The change is written to your audit log. 

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
update_tracking_policy_request = Lockally::UpdateTrackingPolicyRequest.new # UpdateTrackingPolicyRequest | 

begin
  # Update the engagement tracking policy
  result = api_instance.update_tracking_policy(update_tracking_policy_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->update_tracking_policy: #{e}"
end
```

#### Using the update_tracking_policy_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TrackingPolicy>, Integer, Hash)> update_tracking_policy_with_http_info(update_tracking_policy_request)

```ruby
begin
  # Update the engagement tracking policy
  data, status_code, headers = api_instance.update_tracking_policy_with_http_info(update_tracking_policy_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TrackingPolicy>
rescue Lockally::ApiError => e
  puts "Error when calling TenantApi->update_tracking_policy_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **update_tracking_policy_request** | [**UpdateTrackingPolicyRequest**](UpdateTrackingPolicyRequest.md) |  |  |

### Return type

[**TrackingPolicy**](TrackingPolicy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

