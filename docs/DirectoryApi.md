# Lockally::DirectoryApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_directory_activity**](DirectoryApi.md#get_directory_activity) | **GET** /v1/directory-activity | Get recent directory activity |
| [**get_directory_permissions**](DirectoryApi.md#get_directory_permissions) | **GET** /v1/directory-permissions | Get directory permission settings |
| [**get_directory_stats**](DirectoryApi.md#get_directory_stats) | **GET** /v1/directory-stats | Get directory statistics |
| [**get_gal_settings**](DirectoryApi.md#get_gal_settings) | **GET** /v1/gal-settings | Get Global Address List settings |
| [**rebuild_gal_index**](DirectoryApi.md#rebuild_gal_index) | **POST** /v1/gal-settings/rebuild-index | Rebuild the GAL search index |
| [**sync_gal**](DirectoryApi.md#sync_gal) | **POST** /v1/gal-settings/sync | Sync GAL with external directory sources |
| [**update_directory_permissions**](DirectoryApi.md#update_directory_permissions) | **PATCH** /v1/directory-permissions | Update directory permission settings |
| [**update_gal_settings**](DirectoryApi.md#update_gal_settings) | **PATCH** /v1/gal-settings | Update GAL settings |


## get_directory_activity

> <GetDirectoryActivity200Response> get_directory_activity

Get recent directory activity

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Get recent directory activity
  result = api_instance.get_directory_activity
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_activity: #{e}"
end
```

#### Using the get_directory_activity_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDirectoryActivity200Response>, Integer, Hash)> get_directory_activity_with_http_info

```ruby
begin
  # Get recent directory activity
  data, status_code, headers = api_instance.get_directory_activity_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDirectoryActivity200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_activity_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetDirectoryActivity200Response**](GetDirectoryActivity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_directory_permissions

> <DirectoryPermissions> get_directory_permissions

Get directory permission settings

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Get directory permission settings
  result = api_instance.get_directory_permissions
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_permissions: #{e}"
end
```

#### Using the get_directory_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DirectoryPermissions>, Integer, Hash)> get_directory_permissions_with_http_info

```ruby
begin
  # Get directory permission settings
  data, status_code, headers = api_instance.get_directory_permissions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DirectoryPermissions>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_permissions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_directory_stats

> <GetDirectoryStats200Response> get_directory_stats

Get directory statistics

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Get directory statistics
  result = api_instance.get_directory_stats
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_stats: #{e}"
end
```

#### Using the get_directory_stats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDirectoryStats200Response>, Integer, Hash)> get_directory_stats_with_http_info

```ruby
begin
  # Get directory statistics
  data, status_code, headers = api_instance.get_directory_stats_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDirectoryStats200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_directory_stats_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetDirectoryStats200Response**](GetDirectoryStats200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_gal_settings

> <GALSettings> get_gal_settings

Get Global Address List settings

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Get Global Address List settings
  result = api_instance.get_gal_settings
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_gal_settings: #{e}"
end
```

#### Using the get_gal_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GALSettings>, Integer, Hash)> get_gal_settings_with_http_info

```ruby
begin
  # Get Global Address List settings
  data, status_code, headers = api_instance.get_gal_settings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GALSettings>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->get_gal_settings_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## rebuild_gal_index

> <GALSettings> rebuild_gal_index

Rebuild the GAL search index

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Rebuild the GAL search index
  result = api_instance.rebuild_gal_index
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->rebuild_gal_index: #{e}"
end
```

#### Using the rebuild_gal_index_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GALSettings>, Integer, Hash)> rebuild_gal_index_with_http_info

```ruby
begin
  # Rebuild the GAL search index
  data, status_code, headers = api_instance.rebuild_gal_index_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GALSettings>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->rebuild_gal_index_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## sync_gal

> <GALSettings> sync_gal

Sync GAL with external directory sources

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new

begin
  # Sync GAL with external directory sources
  result = api_instance.sync_gal
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->sync_gal: #{e}"
end
```

#### Using the sync_gal_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GALSettings>, Integer, Hash)> sync_gal_with_http_info

```ruby
begin
  # Sync GAL with external directory sources
  data, status_code, headers = api_instance.sync_gal_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GALSettings>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->sync_gal_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_directory_permissions

> <DirectoryPermissions> update_directory_permissions(update_directory_permissions_request)

Update directory permission settings

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new
update_directory_permissions_request = Lockally::UpdateDirectoryPermissionsRequest.new # UpdateDirectoryPermissionsRequest | 

begin
  # Update directory permission settings
  result = api_instance.update_directory_permissions(update_directory_permissions_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->update_directory_permissions: #{e}"
end
```

#### Using the update_directory_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DirectoryPermissions>, Integer, Hash)> update_directory_permissions_with_http_info(update_directory_permissions_request)

```ruby
begin
  # Update directory permission settings
  data, status_code, headers = api_instance.update_directory_permissions_with_http_info(update_directory_permissions_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DirectoryPermissions>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->update_directory_permissions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **update_directory_permissions_request** | [**UpdateDirectoryPermissionsRequest**](UpdateDirectoryPermissionsRequest.md) |  |  |

### Return type

[**DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_gal_settings

> <GALSettings> update_gal_settings(update_gal_settings_request)

Update GAL settings

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DirectoryApi.new
update_gal_settings_request = Lockally::UpdateGALSettingsRequest.new # UpdateGALSettingsRequest | 

begin
  # Update GAL settings
  result = api_instance.update_gal_settings(update_gal_settings_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->update_gal_settings: #{e}"
end
```

#### Using the update_gal_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GALSettings>, Integer, Hash)> update_gal_settings_with_http_info(update_gal_settings_request)

```ruby
begin
  # Update GAL settings
  data, status_code, headers = api_instance.update_gal_settings_with_http_info(update_gal_settings_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GALSettings>
rescue Lockally::ApiError => e
  puts "Error when calling DirectoryApi->update_gal_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **update_gal_settings_request** | [**UpdateGALSettingsRequest**](UpdateGALSettingsRequest.md) |  |  |

### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

