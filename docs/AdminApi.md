# Lockally::AdminApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_admin_login_post**](AdminApi.md#v1_admin_login_post) | **POST** /v1/admin/login | Tenant-admin email+password login |
| [**v1_admin_logout_post**](AdminApi.md#v1_admin_logout_post) | **POST** /v1/admin/logout | Invalidate the current admin session |
| [**v1_admin_me_get**](AdminApi.md#v1_admin_me_get) | **GET** /v1/admin/me | Get the current admin + tenant |


## v1_admin_login_post

> <V1AdminLoginPost200Response> v1_admin_login_post(v1_admin_login_post_request)

Tenant-admin email+password login

Exchanges an admin's email + password for a session token. The web console at `app.lockally.com` posts this on form submission and stores the returned token in an httpOnly cookie.  **No enumeration leak.** Wrong-email and wrong-password both return the same 401 with title \"Invalid credentials\". The argon2id verify runs even on lookup miss (well, structurally — the lookup fails fast but the response shape is constant) so timing leaks are bounded.  Tokens are prefixed `adm_sess_` and valid for 7 days. Use as the `Authorization: Bearer` value on all subsequent calls. 

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::AdminApi.new
v1_admin_login_post_request = Lockally::V1AdminLoginPostRequest.new({email: 'email_example', password: 'password_example'}) # V1AdminLoginPostRequest | 

begin
  # Tenant-admin email+password login
  result = api_instance.v1_admin_login_post(v1_admin_login_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_login_post: #{e}"
end
```

#### Using the v1_admin_login_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1AdminLoginPost200Response>, Integer, Hash)> v1_admin_login_post_with_http_info(v1_admin_login_post_request)

```ruby
begin
  # Tenant-admin email+password login
  data, status_code, headers = api_instance.v1_admin_login_post_with_http_info(v1_admin_login_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1AdminLoginPost200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_login_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_admin_login_post_request** | [**V1AdminLoginPostRequest**](V1AdminLoginPostRequest.md) |  |  |

### Return type

[**V1AdminLoginPost200Response**](V1AdminLoginPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_admin_logout_post

> v1_admin_logout_post

Invalidate the current admin session

Deletes the session row from the database. Idempotent — calling logout on an already-invalid token returns 204 anyway. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminApi.new

begin
  # Invalidate the current admin session
  api_instance.v1_admin_logout_post
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_logout_post: #{e}"
end
```

#### Using the v1_admin_logout_post_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_admin_logout_post_with_http_info

```ruby
begin
  # Invalidate the current admin session
  data, status_code, headers = api_instance.v1_admin_logout_post_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_logout_post_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_admin_me_get

> <V1AdminMeGet200Response> v1_admin_me_get

Get the current admin + tenant

Returns the admin profile + tenant for the session token presented in `Authorization: Bearer`. Used by the web console's layout load function to populate the sidebar.  Returns 403 if called with an API key (lk_live_*) bearer — admin context only exists for session tokens. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminApi.new

begin
  # Get the current admin + tenant
  result = api_instance.v1_admin_me_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_me_get: #{e}"
end
```

#### Using the v1_admin_me_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1AdminMeGet200Response>, Integer, Hash)> v1_admin_me_get_with_http_info

```ruby
begin
  # Get the current admin + tenant
  data, status_code, headers = api_instance.v1_admin_me_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1AdminMeGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AdminApi->v1_admin_me_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1AdminMeGet200Response**](V1AdminMeGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

