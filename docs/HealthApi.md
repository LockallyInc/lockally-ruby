# Lockally::HealthApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**healthz_get**](HealthApi.md#healthz_get) | **GET** /healthz | Liveness check |


## healthz_get

> <HealthzGet200Response> healthz_get

Liveness check

Returns 200 if the process is up and the database pings cleanly. No authentication required.

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::HealthApi.new

begin
  # Liveness check
  result = api_instance.healthz_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling HealthApi->healthz_get: #{e}"
end
```

#### Using the healthz_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<HealthzGet200Response>, Integer, Hash)> healthz_get_with_http_info

```ruby
begin
  # Liveness check
  data, status_code, headers = api_instance.healthz_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <HealthzGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling HealthApi->healthz_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**HealthzGet200Response**](HealthzGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

