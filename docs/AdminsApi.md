# Lockally::AdminsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_admins_get**](AdminsApi.md#v1_admins_get) | **GET** /v1/admins | List tenant admins |
| [**v1_admins_id_delete**](AdminsApi.md#v1_admins_id_delete) | **DELETE** /v1/admins/{id} | Delete an admin |
| [**v1_admins_id_patch**](AdminsApi.md#v1_admins_id_patch) | **PATCH** /v1/admins/{id} | Update an admin |
| [**v1_admins_post**](AdminsApi.md#v1_admins_post) | **POST** /v1/admins | Invite a new admin |


## v1_admins_get

> <V1AdminsGet200Response> v1_admins_get

List tenant admins

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminsApi.new

begin
  # List tenant admins
  result = api_instance.v1_admins_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_get: #{e}"
end
```

#### Using the v1_admins_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1AdminsGet200Response>, Integer, Hash)> v1_admins_get_with_http_info

```ruby
begin
  # List tenant admins
  data, status_code, headers = api_instance.v1_admins_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1AdminsGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1AdminsGet200Response**](V1AdminsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_admins_id_delete

> v1_admins_id_delete(id)

Delete an admin

Hard-delete. Cascade-drops the admin's sessions (immediate revocation). Same safety rails as PATCH disabled=true. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete an admin
  api_instance.v1_admins_id_delete(id)
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_id_delete: #{e}"
end
```

#### Using the v1_admins_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_admins_id_delete_with_http_info(id)

```ruby
begin
  # Delete an admin
  data, status_code, headers = api_instance.v1_admins_id_delete_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_id_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_admins_id_patch

> <AdminFull> v1_admins_id_patch(id, v1_admins_id_patch_request)

Update an admin

Supply at least one of `password`, `display_name`, `role`, `disabled`.  **Safety rails.** A session bearer (adm_sess_*) cannot disable itself — use another admin or an API key (which bypasses the self-rail). Disabling the last active admin returns 409 to prevent orphaning the tenant from its console. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
v1_admins_id_patch_request = Lockally::V1AdminsIdPatchRequest.new # V1AdminsIdPatchRequest | 

begin
  # Update an admin
  result = api_instance.v1_admins_id_patch(id, v1_admins_id_patch_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_id_patch: #{e}"
end
```

#### Using the v1_admins_id_patch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AdminFull>, Integer, Hash)> v1_admins_id_patch_with_http_info(id, v1_admins_id_patch_request)

```ruby
begin
  # Update an admin
  data, status_code, headers = api_instance.v1_admins_id_patch_with_http_info(id, v1_admins_id_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AdminFull>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_id_patch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **v1_admins_id_patch_request** | [**V1AdminsIdPatchRequest**](V1AdminsIdPatchRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_admins_post

> <AdminFull> v1_admins_post(v1_admins_post_request)

Invite a new admin

Creates a new tenant admin. If `password` is omitted, lockally generates a 16-char password and returns it ONCE in the response. Email is case-insensitive and unique per tenant. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AdminsApi.new
v1_admins_post_request = Lockally::V1AdminsPostRequest.new({email: 'email_example'}) # V1AdminsPostRequest | 

begin
  # Invite a new admin
  result = api_instance.v1_admins_post(v1_admins_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_post: #{e}"
end
```

#### Using the v1_admins_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AdminFull>, Integer, Hash)> v1_admins_post_with_http_info(v1_admins_post_request)

```ruby
begin
  # Invite a new admin
  data, status_code, headers = api_instance.v1_admins_post_with_http_info(v1_admins_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AdminFull>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->v1_admins_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_admins_post_request** | [**V1AdminsPostRequest**](V1AdminsPostRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

