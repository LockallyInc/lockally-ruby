# Lockally::TemplatesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_template**](TemplatesApi.md#create_template) | **POST** /v1/templates | Create a template |
| [**delete_template**](TemplatesApi.md#delete_template) | **DELETE** /v1/templates/{id} | Delete a template |
| [**get_template**](TemplatesApi.md#get_template) | **GET** /v1/templates/{id} | Get a template |
| [**list_templates**](TemplatesApi.md#list_templates) | **GET** /v1/templates | List templates |
| [**update_template**](TemplatesApi.md#update_template) | **PUT** /v1/templates/{id} | Update a template |


## create_template

> <Template> create_template(template_input)

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
  result = api_instance.create_template(template_input)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->create_template: #{e}"
end
```

#### Using the create_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> create_template_with_http_info(template_input)

```ruby
begin
  # Create a template
  data, status_code, headers = api_instance.create_template_with_http_info(template_input)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->create_template_with_http_info: #{e}"
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


## delete_template

> delete_template(id)

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
  api_instance.delete_template(id)
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->delete_template: #{e}"
end
```

#### Using the delete_template_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_template_with_http_info(id)

```ruby
begin
  # Delete a template
  data, status_code, headers = api_instance.delete_template_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->delete_template_with_http_info: #{e}"
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


## get_template

> <Template> get_template(id)

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
  result = api_instance.get_template(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->get_template: #{e}"
end
```

#### Using the get_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> get_template_with_http_info(id)

```ruby
begin
  # Get a template
  data, status_code, headers = api_instance.get_template_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->get_template_with_http_info: #{e}"
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


## list_templates

> <ListTemplates200Response> list_templates

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
  result = api_instance.list_templates
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->list_templates: #{e}"
end
```

#### Using the list_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListTemplates200Response>, Integer, Hash)> list_templates_with_http_info

```ruby
begin
  # List templates
  data, status_code, headers = api_instance.list_templates_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListTemplates200Response>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->list_templates_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListTemplates200Response**](ListTemplates200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_template

> <Template> update_template(id, template_input)

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
  result = api_instance.update_template(id, template_input)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->update_template: #{e}"
end
```

#### Using the update_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Template>, Integer, Hash)> update_template_with_http_info(id, template_input)

```ruby
begin
  # Update a template
  data, status_code, headers = api_instance.update_template_with_http_info(id, template_input)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Template>
rescue Lockally::ApiError => e
  puts "Error when calling TemplatesApi->update_template_with_http_info: #{e}"
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

