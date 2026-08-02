# Lockally::DashboardApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_audit_summary**](DashboardApi.md#get_audit_summary) | **GET** /v1/audit-summary | Audit summary for the dashboard |
| [**get_domains_status**](DashboardApi.md#get_domains_status) | **GET** /v1/domains/status | Domain health status for the dashboard |
| [**get_integrations_summary**](DashboardApi.md#get_integrations_summary) | **GET** /v1/integrations-summary | Integrations summary for the dashboard |
| [**get_security**](DashboardApi.md#get_security) | **GET** /v1/security | Security overview for the dashboard |
| [**get_storage**](DashboardApi.md#get_storage) | **GET** /v1/storage | Storage usage for the dashboard |
| [**get_tenant_health**](DashboardApi.md#get_tenant_health) | **GET** /v1/health | Full tenant health report |
| [**get_user_insights**](DashboardApi.md#get_user_insights) | **GET** /v1/user-insights | User insights for the dashboard |


## get_audit_summary

> <GetAuditSummary200Response> get_audit_summary

Audit summary for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Audit summary for the dashboard
  result = api_instance.get_audit_summary
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_audit_summary: #{e}"
end
```

#### Using the get_audit_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAuditSummary200Response>, Integer, Hash)> get_audit_summary_with_http_info

```ruby
begin
  # Audit summary for the dashboard
  data, status_code, headers = api_instance.get_audit_summary_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAuditSummary200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_audit_summary_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetAuditSummary200Response**](GetAuditSummary200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_domains_status

> <GetDomainsStatus200Response> get_domains_status

Domain health status for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Domain health status for the dashboard
  result = api_instance.get_domains_status
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_domains_status: #{e}"
end
```

#### Using the get_domains_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDomainsStatus200Response>, Integer, Hash)> get_domains_status_with_http_info

```ruby
begin
  # Domain health status for the dashboard
  data, status_code, headers = api_instance.get_domains_status_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDomainsStatus200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_domains_status_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetDomainsStatus200Response**](GetDomainsStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_integrations_summary

> <GetIntegrationsSummary200Response> get_integrations_summary

Integrations summary for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Integrations summary for the dashboard
  result = api_instance.get_integrations_summary
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_integrations_summary: #{e}"
end
```

#### Using the get_integrations_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetIntegrationsSummary200Response>, Integer, Hash)> get_integrations_summary_with_http_info

```ruby
begin
  # Integrations summary for the dashboard
  data, status_code, headers = api_instance.get_integrations_summary_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetIntegrationsSummary200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_integrations_summary_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetIntegrationsSummary200Response**](GetIntegrationsSummary200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_security

> <GetSecurity200Response> get_security

Security overview for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Security overview for the dashboard
  result = api_instance.get_security
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_security: #{e}"
end
```

#### Using the get_security_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSecurity200Response>, Integer, Hash)> get_security_with_http_info

```ruby
begin
  # Security overview for the dashboard
  data, status_code, headers = api_instance.get_security_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSecurity200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_security_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetSecurity200Response**](GetSecurity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_storage

> <GetStorage200Response> get_storage

Storage usage for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Storage usage for the dashboard
  result = api_instance.get_storage
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_storage: #{e}"
end
```

#### Using the get_storage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetStorage200Response>, Integer, Hash)> get_storage_with_http_info

```ruby
begin
  # Storage usage for the dashboard
  data, status_code, headers = api_instance.get_storage_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetStorage200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_storage_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetStorage200Response**](GetStorage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_tenant_health

> Object get_tenant_health

Full tenant health report

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # Full tenant health report
  result = api_instance.get_tenant_health
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_tenant_health: #{e}"
end
```

#### Using the get_tenant_health_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> get_tenant_health_with_http_info

```ruby
begin
  # Full tenant health report
  data, status_code, headers = api_instance.get_tenant_health_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_tenant_health_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_user_insights

> <GetUserInsights200Response> get_user_insights

User insights for the dashboard

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DashboardApi.new

begin
  # User insights for the dashboard
  result = api_instance.get_user_insights
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_user_insights: #{e}"
end
```

#### Using the get_user_insights_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetUserInsights200Response>, Integer, Hash)> get_user_insights_with_http_info

```ruby
begin
  # User insights for the dashboard
  data, status_code, headers = api_instance.get_user_insights_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetUserInsights200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DashboardApi->get_user_insights_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetUserInsights200Response**](GetUserInsights200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

