# Lockally::AdminsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_admin**](AdminsApi.md#delete_admin) | **DELETE** /v1/admins/{id} | Delete an admin |
| [**invite_admin**](AdminsApi.md#invite_admin) | **POST** /v1/admins | Invite a new admin |
| [**list_admins**](AdminsApi.md#list_admins) | **GET** /v1/admins | List tenant admins |
| [**update_admin**](AdminsApi.md#update_admin) | **PATCH** /v1/admins/{id} | Update an admin |


## delete_admin

> delete_admin(id)

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
  api_instance.delete_admin(id)
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->delete_admin: #{e}"
end
```

#### Using the delete_admin_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_admin_with_http_info(id)

```ruby
begin
  # Delete an admin
  data, status_code, headers = api_instance.delete_admin_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->delete_admin_with_http_info: #{e}"
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


## invite_admin

> <AdminFull> invite_admin(invite_admin_request)

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
invite_admin_request = Lockally::InviteAdminRequest.new({email: 'email_example'}) # InviteAdminRequest | 

begin
  # Invite a new admin
  result = api_instance.invite_admin(invite_admin_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->invite_admin: #{e}"
end
```

#### Using the invite_admin_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AdminFull>, Integer, Hash)> invite_admin_with_http_info(invite_admin_request)

```ruby
begin
  # Invite a new admin
  data, status_code, headers = api_instance.invite_admin_with_http_info(invite_admin_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AdminFull>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->invite_admin_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **invite_admin_request** | [**InviteAdminRequest**](InviteAdminRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## list_admins

> <ListAdmins200Response> list_admins

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
  result = api_instance.list_admins
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->list_admins: #{e}"
end
```

#### Using the list_admins_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListAdmins200Response>, Integer, Hash)> list_admins_with_http_info

```ruby
begin
  # List tenant admins
  data, status_code, headers = api_instance.list_admins_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListAdmins200Response>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->list_admins_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListAdmins200Response**](ListAdmins200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_admin

> <AdminFull> update_admin(id, update_admin_request)

Update an admin

Supply at least one of `password`, `display_name`, `role`, `disabled`.  **Safety rails.** A session bearer (adm_sess_*) cannot disable itself, use another admin or an API key (which bypasses the self-rail). Disabling the last active admin returns 409 to prevent orphaning the tenant from its console. 

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
update_admin_request = Lockally::UpdateAdminRequest.new # UpdateAdminRequest | 

begin
  # Update an admin
  result = api_instance.update_admin(id, update_admin_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->update_admin: #{e}"
end
```

#### Using the update_admin_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AdminFull>, Integer, Hash)> update_admin_with_http_info(id, update_admin_request)

```ruby
begin
  # Update an admin
  data, status_code, headers = api_instance.update_admin_with_http_info(id, update_admin_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AdminFull>
rescue Lockally::ApiError => e
  puts "Error when calling AdminsApi->update_admin_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_admin_request** | [**UpdateAdminRequest**](UpdateAdminRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

