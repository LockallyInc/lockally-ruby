# Lockally::HealthApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**health_check**](HealthApi.md#health_check) | **GET** /healthz | Liveness check |


## health_check

> <HealthCheck200Response> health_check

Liveness check

Returns 200 if the process is up and the database pings cleanly. No authentication required.

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::HealthApi.new

begin
  # Liveness check
  result = api_instance.health_check
  p result
rescue Lockally::ApiError => e
  puts "Error when calling HealthApi->health_check: #{e}"
end
```

#### Using the health_check_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<HealthCheck200Response>, Integer, Hash)> health_check_with_http_info

```ruby
begin
  # Liveness check
  data, status_code, headers = api_instance.health_check_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <HealthCheck200Response>
rescue Lockally::ApiError => e
  puts "Error when calling HealthApi->health_check_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**HealthCheck200Response**](HealthCheck200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

