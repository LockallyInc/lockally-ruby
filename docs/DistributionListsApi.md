# Lockally::DistributionListsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_distribution_list**](DistributionListsApi.md#create_distribution_list) | **POST** /v1/distribution-lists | Create a distribution list |
| [**delete_distribution_list**](DistributionListsApi.md#delete_distribution_list) | **DELETE** /v1/distribution-lists/{address} | Delete a distribution list |
| [**get_distribution_list**](DistributionListsApi.md#get_distribution_list) | **GET** /v1/distribution-lists/{address} | Get a distribution list |
| [**list_distribution_lists**](DistributionListsApi.md#list_distribution_lists) | **GET** /v1/distribution-lists | List distribution lists |
| [**replace_distribution_list_members**](DistributionListsApi.md#replace_distribution_list_members) | **PUT** /v1/distribution-lists/{address}/members | Replace distribution list members |


## create_distribution_list

> <DistributionListDetail> create_distribution_list(create_distribution_list_request)

Create a distribution list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DistributionListsApi.new
create_distribution_list_request = Lockally::CreateDistributionListRequest.new({list_address: 'list_address_example'}) # CreateDistributionListRequest | 

begin
  # Create a distribution list
  result = api_instance.create_distribution_list(create_distribution_list_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->create_distribution_list: #{e}"
end
```

#### Using the create_distribution_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DistributionListDetail>, Integer, Hash)> create_distribution_list_with_http_info(create_distribution_list_request)

```ruby
begin
  # Create a distribution list
  data, status_code, headers = api_instance.create_distribution_list_with_http_info(create_distribution_list_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DistributionListDetail>
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->create_distribution_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_distribution_list_request** | [**CreateDistributionListRequest**](CreateDistributionListRequest.md) |  |  |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_distribution_list

> delete_distribution_list(address)

Delete a distribution list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DistributionListsApi.new
address = 'address_example' # String | Distribution list email address

begin
  # Delete a distribution list
  api_instance.delete_distribution_list(address)
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->delete_distribution_list: #{e}"
end
```

#### Using the delete_distribution_list_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_distribution_list_with_http_info(address)

```ruby
begin
  # Delete a distribution list
  data, status_code, headers = api_instance.delete_distribution_list_with_http_info(address)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->delete_distribution_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address** | **String** | Distribution list email address |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## get_distribution_list

> <DistributionListDetail> get_distribution_list(address)

Get a distribution list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DistributionListsApi.new
address = 'address_example' # String | Distribution list email address

begin
  # Get a distribution list
  result = api_instance.get_distribution_list(address)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->get_distribution_list: #{e}"
end
```

#### Using the get_distribution_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DistributionListDetail>, Integer, Hash)> get_distribution_list_with_http_info(address)

```ruby
begin
  # Get a distribution list
  data, status_code, headers = api_instance.get_distribution_list_with_http_info(address)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DistributionListDetail>
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->get_distribution_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address** | **String** | Distribution list email address |  |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_distribution_lists

> <ListDistributionLists200Response> list_distribution_lists

List distribution lists

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DistributionListsApi.new

begin
  # List distribution lists
  result = api_instance.list_distribution_lists
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->list_distribution_lists: #{e}"
end
```

#### Using the list_distribution_lists_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListDistributionLists200Response>, Integer, Hash)> list_distribution_lists_with_http_info

```ruby
begin
  # List distribution lists
  data, status_code, headers = api_instance.list_distribution_lists_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListDistributionLists200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->list_distribution_lists_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListDistributionLists200Response**](ListDistributionLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## replace_distribution_list_members

> <ReplaceDistributionListMembers200Response> replace_distribution_list_members(address, replace_distribution_list_members_request)

Replace distribution list members

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DistributionListsApi.new
address = 'address_example' # String | Distribution list email address
replace_distribution_list_members_request = Lockally::ReplaceDistributionListMembersRequest.new({members: ['members_example']}) # ReplaceDistributionListMembersRequest | 

begin
  # Replace distribution list members
  result = api_instance.replace_distribution_list_members(address, replace_distribution_list_members_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->replace_distribution_list_members: #{e}"
end
```

#### Using the replace_distribution_list_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReplaceDistributionListMembers200Response>, Integer, Hash)> replace_distribution_list_members_with_http_info(address, replace_distribution_list_members_request)

```ruby
begin
  # Replace distribution list members
  data, status_code, headers = api_instance.replace_distribution_list_members_with_http_info(address, replace_distribution_list_members_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReplaceDistributionListMembers200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DistributionListsApi->replace_distribution_list_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address** | **String** | Distribution list email address |  |
| **replace_distribution_list_members_request** | [**ReplaceDistributionListMembersRequest**](ReplaceDistributionListMembersRequest.md) |  |  |

### Return type

[**ReplaceDistributionListMembers200Response**](ReplaceDistributionListMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

