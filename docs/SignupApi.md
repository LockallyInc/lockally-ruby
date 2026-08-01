# Lockally::SignupApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**signup**](SignupApi.md#signup) | **POST** /v1/signup | Sign up a new tenant |


## signup

> <V1AdminLoginPost200Response> signup(signup_request)

Sign up a new tenant

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::SignupApi.new
signup_request = Lockally::SignupRequest.new({slug: 'slug_example', admin_email: 'admin_email_example', password: 'password_example'}) # SignupRequest | 

begin
  # Sign up a new tenant
  result = api_instance.signup(signup_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling SignupApi->signup: #{e}"
end
```

#### Using the signup_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1AdminLoginPost200Response>, Integer, Hash)> signup_with_http_info(signup_request)

```ruby
begin
  # Sign up a new tenant
  data, status_code, headers = api_instance.signup_with_http_info(signup_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1AdminLoginPost200Response>
rescue Lockally::ApiError => e
  puts "Error when calling SignupApi->signup_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **signup_request** | [**SignupRequest**](SignupRequest.md) |  |  |

### Return type

[**V1AdminLoginPost200Response**](V1AdminLoginPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

