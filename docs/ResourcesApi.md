# Lockally::ResourcesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_resource**](ResourcesApi.md#create_resource) | **POST** /v1/resources | Create a resource |
| [**delete_resource**](ResourcesApi.md#delete_resource) | **DELETE** /v1/resources/{id} | Delete a resource |
| [**get_resource**](ResourcesApi.md#get_resource) | **GET** /v1/resources/{id} | Get a resource |
| [**list_resources**](ResourcesApi.md#list_resources) | **GET** /v1/resources | List resources |
| [**update_resource**](ResourcesApi.md#update_resource) | **PATCH** /v1/resources/{id} | Update a resource |


## create_resource

> <Resource> create_resource(create_resource_request)

Create a resource

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ResourcesApi.new
create_resource_request = Lockally::CreateResourceRequest.new({name: 'name_example'}) # CreateResourceRequest | 

begin
  # Create a resource
  result = api_instance.create_resource(create_resource_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->create_resource: #{e}"
end
```

#### Using the create_resource_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Resource>, Integer, Hash)> create_resource_with_http_info(create_resource_request)

```ruby
begin
  # Create a resource
  data, status_code, headers = api_instance.create_resource_with_http_info(create_resource_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Resource>
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->create_resource_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_resource_request** | [**CreateResourceRequest**](CreateResourceRequest.md) |  |  |

### Return type

[**Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_resource

> delete_resource(id)

Delete a resource

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ResourcesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a resource
  api_instance.delete_resource(id)
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->delete_resource: #{e}"
end
```

#### Using the delete_resource_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_resource_with_http_info(id)

```ruby
begin
  # Delete a resource
  data, status_code, headers = api_instance.delete_resource_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->delete_resource_with_http_info: #{e}"
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


## get_resource

> <Resource> get_resource(id)

Get a resource

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ResourcesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a resource
  result = api_instance.get_resource(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->get_resource: #{e}"
end
```

#### Using the get_resource_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Resource>, Integer, Hash)> get_resource_with_http_info(id)

```ruby
begin
  # Get a resource
  data, status_code, headers = api_instance.get_resource_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Resource>
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->get_resource_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_resources

> <ListResources200Response> list_resources

List resources

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ResourcesApi.new

begin
  # List resources
  result = api_instance.list_resources
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->list_resources: #{e}"
end
```

#### Using the list_resources_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListResources200Response>, Integer, Hash)> list_resources_with_http_info

```ruby
begin
  # List resources
  data, status_code, headers = api_instance.list_resources_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListResources200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->list_resources_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListResources200Response**](ListResources200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_resource

> <Resource> update_resource(id, update_resource_request)

Update a resource

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ResourcesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_resource_request = Lockally::UpdateResourceRequest.new # UpdateResourceRequest | 

begin
  # Update a resource
  result = api_instance.update_resource(id, update_resource_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->update_resource: #{e}"
end
```

#### Using the update_resource_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Resource>, Integer, Hash)> update_resource_with_http_info(id, update_resource_request)

```ruby
begin
  # Update a resource
  data, status_code, headers = api_instance.update_resource_with_http_info(id, update_resource_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Resource>
rescue Lockally::ApiError => e
  puts "Error when calling ResourcesApi->update_resource_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_resource_request** | [**UpdateResourceRequest**](UpdateResourceRequest.md) |  |  |

### Return type

[**Resource**](Resource.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

