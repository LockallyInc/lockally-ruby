# Lockally::UsersApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_user**](UsersApi.md#create_user) | **POST** /v1/users | Create a user |
| [**delete_user**](UsersApi.md#delete_user) | **DELETE** /v1/users/{id} | Delete a user |
| [**get_user**](UsersApi.md#get_user) | **GET** /v1/users/{id} | Get a user |
| [**list_users**](UsersApi.md#list_users) | **GET** /v1/users | List users |
| [**update_user**](UsersApi.md#update_user) | **PATCH** /v1/users/{id} | Update a user |


## create_user

> <User> create_user(create_user_request)

Create a user

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::UsersApi.new
create_user_request = Lockally::CreateUserRequest.new({email: 'email_example', first_name: 'first_name_example', last_name: 'last_name_example'}) # CreateUserRequest | 

begin
  # Create a user
  result = api_instance.create_user(create_user_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->create_user: #{e}"
end
```

#### Using the create_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<User>, Integer, Hash)> create_user_with_http_info(create_user_request)

```ruby
begin
  # Create a user
  data, status_code, headers = api_instance.create_user_with_http_info(create_user_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <User>
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->create_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_user_request** | [**CreateUserRequest**](CreateUserRequest.md) |  |  |

### Return type

[**User**](User.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_user

> delete_user(id)

Delete a user

Soft-deletes the user by setting status to deprovisioned.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::UsersApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a user
  api_instance.delete_user(id)
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->delete_user: #{e}"
end
```

#### Using the delete_user_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_user_with_http_info(id)

```ruby
begin
  # Delete a user
  data, status_code, headers = api_instance.delete_user_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->delete_user_with_http_info: #{e}"
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


## get_user

> <User> get_user(id)

Get a user

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::UsersApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a user
  result = api_instance.get_user(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->get_user: #{e}"
end
```

#### Using the get_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<User>, Integer, Hash)> get_user_with_http_info(id)

```ruby
begin
  # Get a user
  data, status_code, headers = api_instance.get_user_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <User>
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->get_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**User**](User.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_users

> <ListUsers200Response> list_users(opts)

List users

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::UsersApi.new
opts = {
  limit: 56 # Integer | 
}

begin
  # List users
  result = api_instance.list_users(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->list_users: #{e}"
end
```

#### Using the list_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListUsers200Response>, Integer, Hash)> list_users_with_http_info(opts)

```ruby
begin
  # List users
  data, status_code, headers = api_instance.list_users_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListUsers200Response>
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->list_users_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional][default to 100] |

### Return type

[**ListUsers200Response**](ListUsers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_user

> <User> update_user(id, update_user_request)

Update a user

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::UsersApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_user_request = Lockally::UpdateUserRequest.new # UpdateUserRequest | 

begin
  # Update a user
  result = api_instance.update_user(id, update_user_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->update_user: #{e}"
end
```

#### Using the update_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<User>, Integer, Hash)> update_user_with_http_info(id, update_user_request)

```ruby
begin
  # Update a user
  data, status_code, headers = api_instance.update_user_with_http_info(id, update_user_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <User>
rescue Lockally::ApiError => e
  puts "Error when calling UsersApi->update_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_user_request** | [**UpdateUserRequest**](UpdateUserRequest.md) |  |  |

### Return type

[**User**](User.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

