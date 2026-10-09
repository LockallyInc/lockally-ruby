# Lockally::TemplatesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_templates_get**](TemplatesApi.md#v1_templates_get) | **GET** /v1/templates | List templates |
| [**v1_templates_id_delete**](TemplatesApi.md#v1_templates_id_delete) | **DELETE** /v1/templates/{id} | Delete a template |
| [**v1_templates_id_get**](TemplatesApi.md#v1_templates_id_get) | **GET** /v1/templates/{id} | Get a template |
| [**v1_templates_id_put**](TemplatesApi.md#v1_templates_id_put) | **PUT** /v1/templates/{id} | Update a template |
| [**v1_templates_post**](TemplatesApi.md#v1_templates_post) | **POST** /v1/templates | Create a template |


## v1_templates_get

> <V1TemplatesGet200Response> v1_templates_get

List templates

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TemplatesApi.new

begin
  # List templates
  result = api_instance.v1_templates_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_get: #{e}"
end
```

#### Using the v1_templates_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1TemplatesGet200Response>, Integer, Hash)> v1_templates_get_with_http_info

```ruby
begin
  # List templates
  data, status_code, headers = api_instance.v1_templates_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1TemplatesGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1TemplatesGet200Response**](V1TemplatesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_templates_id_delete

> v1_templates_id_delete(id)

Delete a template

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TemplatesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a template
  api_instance.v1_templates_id_delete(id)
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_delete: #{e}"
end
```

#### Using the v1_templates_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_templates_id_delete_with_http_info(id)

```ruby
begin
  # Delete a template
  data, status_code, headers = api_instance.v1_templates_id_delete_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_delete_with_http_info: #{e}"
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


## v1_templates_id_get

> <Template> v1_templates_id_get(id)

Get a template

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TemplatesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a template
  result = api_instance.v1_templates_id_get(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_get: #{e}"
end
```

#### Using the v1_templates_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> v1_templates_id_get_with_http_info(id)

```ruby
begin
  # Get a template
  data, status_code, headers = api_instance.v1_templates_id_get_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_templates_id_put

> <Template> v1_templates_id_put(id, template_input)

Update a template

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TemplatesApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
template_input = Lockally::TemplateInput.new({name: 'name_example'}) # TemplateInput | 

begin
  # Update a template
  result = api_instance.v1_templates_id_put(id, template_input)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_put: #{e}"
end
```

#### Using the v1_templates_id_put_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> v1_templates_id_put_with_http_info(id, template_input)

```ruby
begin
  # Update a template
  data, status_code, headers = api_instance.v1_templates_id_put_with_http_info(id, template_input)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_id_put_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **template_input** | [**TemplateInput**](TemplateInput.md) |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_templates_post

> <Template> v1_templates_post(template_input)

Create a template

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TemplatesApi.new
template_input = Lockally::TemplateInput.new({name: 'name_example'}) # TemplateInput | 

begin
  # Create a template
  result = api_instance.v1_templates_post(template_input)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_post: #{e}"
end
```

#### Using the v1_templates_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> v1_templates_post_with_http_info(template_input)

```ruby
begin
  # Create a template
  data, status_code, headers = api_instance.v1_templates_post_with_http_info(template_input)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->v1_templates_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_input** | [**TemplateInput**](TemplateInput.md) |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

