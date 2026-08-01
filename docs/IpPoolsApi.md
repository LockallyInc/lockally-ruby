# Lockally::IpPoolsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_dedicated_ip_request**](IpPoolsApi.md#create_dedicated_ip_request) | **POST** /v1/dedicated-ip-requests | Request a dedicated IP |
| [**get_ip_assignment**](IpPoolsApi.md#get_ip_assignment) | **GET** /v1/ip-assignment | Get current IP assignment |
| [**list_dedicated_ip_requests**](IpPoolsApi.md#list_dedicated_ip_requests) | **GET** /v1/dedicated-ip-requests | List dedicated IP requests |


## create_dedicated_ip_request

> <DedicatedIPRequest> create_dedicated_ip_request(create_dedicated_ip_request_request)

Request a dedicated IP

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::IpPoolsApi.new
create_dedicated_ip_request_request = Lockally::CreateDedicatedIPRequestRequest.new({note: 'note_example'}) # CreateDedicatedIPRequestRequest | 

begin
  # Request a dedicated IP
  result = api_instance.create_dedicated_ip_request(create_dedicated_ip_request_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->create_dedicated_ip_request: #{e}"
end
```

#### Using the create_dedicated_ip_request_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DedicatedIPRequest>, Integer, Hash)> create_dedicated_ip_request_with_http_info(create_dedicated_ip_request_request)

```ruby
begin
  # Request a dedicated IP
  data, status_code, headers = api_instance.create_dedicated_ip_request_with_http_info(create_dedicated_ip_request_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DedicatedIPRequest>
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->create_dedicated_ip_request_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_dedicated_ip_request_request** | [**CreateDedicatedIPRequestRequest**](CreateDedicatedIPRequestRequest.md) |  |  |

### Return type

[**DedicatedIPRequest**](DedicatedIPRequest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## get_ip_assignment

> <GetIPAssignment200Response> get_ip_assignment

Get current IP assignment

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::IpPoolsApi.new

begin
  # Get current IP assignment
  result = api_instance.get_ip_assignment
  p result
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->get_ip_assignment: #{e}"
end
```

#### Using the get_ip_assignment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetIPAssignment200Response>, Integer, Hash)> get_ip_assignment_with_http_info

```ruby
begin
  # Get current IP assignment
  data, status_code, headers = api_instance.get_ip_assignment_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetIPAssignment200Response>
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->get_ip_assignment_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetIPAssignment200Response**](GetIPAssignment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_dedicated_ip_requests

> <ListDedicatedIPRequests200Response> list_dedicated_ip_requests

List dedicated IP requests

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::IpPoolsApi.new

begin
  # List dedicated IP requests
  result = api_instance.list_dedicated_ip_requests
  p result
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->list_dedicated_ip_requests: #{e}"
end
```

#### Using the list_dedicated_ip_requests_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListDedicatedIPRequests200Response>, Integer, Hash)> list_dedicated_ip_requests_with_http_info

```ruby
begin
  # List dedicated IP requests
  data, status_code, headers = api_instance.list_dedicated_ip_requests_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListDedicatedIPRequests200Response>
rescue Lockally::ApiError => e
  puts "Error when calling IpPoolsApi->list_dedicated_ip_requests_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListDedicatedIPRequests200Response**](ListDedicatedIPRequests200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

