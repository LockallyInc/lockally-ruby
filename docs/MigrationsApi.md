# Lockally::MigrationsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**cancel_migration**](MigrationsApi.md#cancel_migration) | **POST** /v1/migrations/{id}/cancel | Cancel a running migration |
| [**check_migration_dns**](MigrationsApi.md#check_migration_dns) | **GET** /v1/migrations/{id}/dns-check | Check DNS readiness for cutover |
| [**create_migration**](MigrationsApi.md#create_migration) | **POST** /v1/migrations | Create a migration |
| [**create_migration_credential**](MigrationsApi.md#create_migration_credential) | **POST** /v1/migrations/credentials | Store a migration credential |
| [**delete_migration**](MigrationsApi.md#delete_migration) | **DELETE** /v1/migrations/{id} | Delete a migration |
| [**delete_migration_credential**](MigrationsApi.md#delete_migration_credential) | **DELETE** /v1/migrations/credentials/{id} | Delete a migration credential |
| [**delta_sync_migration**](MigrationsApi.md#delta_sync_migration) | **POST** /v1/migrations/{id}/delta-sync | Run a delta sync |
| [**discover_migration**](MigrationsApi.md#discover_migration) | **POST** /v1/migrations/{id}/discover | Discover source mailboxes |
| [**final_sync_migration**](MigrationsApi.md#final_sync_migration) | **POST** /v1/migrations/{id}/final-sync | Run the final sync before cutover |
| [**get_migration**](MigrationsApi.md#get_migration) | **GET** /v1/migrations/{id} | Get a migration |
| [**get_migration_progress**](MigrationsApi.md#get_migration_progress) | **GET** /v1/migrations/{id}/progress | Get migration progress |
| [**list_migration_credentials**](MigrationsApi.md#list_migration_credentials) | **GET** /v1/migrations/credentials | List migration credentials |
| [**list_migration_events**](MigrationsApi.md#list_migration_events) | **GET** /v1/migrations/{id}/events | List migration events |
| [**list_migration_mailboxes**](MigrationsApi.md#list_migration_mailboxes) | **GET** /v1/migrations/{id}/mailboxes | List migration mailboxes |
| [**list_migrations**](MigrationsApi.md#list_migrations) | **GET** /v1/migrations | List migrations |
| [**map_migration**](MigrationsApi.md#map_migration) | **POST** /v1/migrations/{id}/map | Map source to destination mailboxes |
| [**retry_migration**](MigrationsApi.md#retry_migration) | **POST** /v1/migrations/{id}/retry | Retry a failed or cancelled migration |
| [**start_migration**](MigrationsApi.md#start_migration) | **POST** /v1/migrations/{id}/start | Start the migration |
| [**update_migration**](MigrationsApi.md#update_migration) | **PATCH** /v1/migrations/{id} | Update a migration |
| [**update_migration_mailbox**](MigrationsApi.md#update_migration_mailbox) | **PATCH** /v1/migrations/{id}/mailboxes/{mbxId} | Update a migration mailbox |
| [**validate_migration**](MigrationsApi.md#validate_migration) | **POST** /v1/migrations/{id}/validate | Validate migrated data |


## cancel_migration

> <DiscoverMigration202Response> cancel_migration(id)

Cancel a running migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Cancel a running migration
  result = api_instance.cancel_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->cancel_migration: #{e}"
end
```

#### Using the cancel_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoverMigration202Response>, Integer, Hash)> cancel_migration_with_http_info(id)

```ruby
begin
  # Cancel a running migration
  data, status_code, headers = api_instance.cancel_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoverMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->cancel_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## check_migration_dns

> Object check_migration_dns(id)

Check DNS readiness for cutover

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Check DNS readiness for cutover
  result = api_instance.check_migration_dns(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->check_migration_dns: #{e}"
end
```

#### Using the check_migration_dns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> check_migration_dns_with_http_info(id)

```ruby
begin
  # Check DNS readiness for cutover
  data, status_code, headers = api_instance.check_migration_dns_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->check_migration_dns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## create_migration

> <Migration> create_migration(create_migration_request)

Create a migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
create_migration_request = Lockally::CreateMigrationRequest.new({name: 'name_example', credential_id: 'credential_id_example', source_provider: 'source_provider_example'}) # CreateMigrationRequest | 

begin
  # Create a migration
  result = api_instance.create_migration(create_migration_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->create_migration: #{e}"
end
```

#### Using the create_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Migration>, Integer, Hash)> create_migration_with_http_info(create_migration_request)

```ruby
begin
  # Create a migration
  data, status_code, headers = api_instance.create_migration_with_http_info(create_migration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Migration>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->create_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_migration_request** | [**CreateMigrationRequest**](CreateMigrationRequest.md) |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_migration_credential

> <MigrationCredential> create_migration_credential(create_migration_credential_request)

Store a migration credential

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
create_migration_credential_request = Lockally::CreateMigrationCredentialRequest.new({provider: 'imap', credentials: Lockally::CreateMigrationCredentialRequestCredentials.new({host: 'host_example', port: 37})}) # CreateMigrationCredentialRequest | 

begin
  # Store a migration credential
  result = api_instance.create_migration_credential(create_migration_credential_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->create_migration_credential: #{e}"
end
```

#### Using the create_migration_credential_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MigrationCredential>, Integer, Hash)> create_migration_credential_with_http_info(create_migration_credential_request)

```ruby
begin
  # Store a migration credential
  data, status_code, headers = api_instance.create_migration_credential_with_http_info(create_migration_credential_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MigrationCredential>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->create_migration_credential_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_migration_credential_request** | [**CreateMigrationCredentialRequest**](CreateMigrationCredentialRequest.md) |  |  |

### Return type

[**MigrationCredential**](MigrationCredential.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_migration

> delete_migration(id)

Delete a migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a migration
  api_instance.delete_migration(id)
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delete_migration: #{e}"
end
```

#### Using the delete_migration_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_migration_with_http_info(id)

```ruby
begin
  # Delete a migration
  data, status_code, headers = api_instance.delete_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delete_migration_with_http_info: #{e}"
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


## delete_migration_credential

> delete_migration_credential(id)

Delete a migration credential

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a migration credential
  api_instance.delete_migration_credential(id)
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delete_migration_credential: #{e}"
end
```

#### Using the delete_migration_credential_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_migration_credential_with_http_info(id)

```ruby
begin
  # Delete a migration credential
  data, status_code, headers = api_instance.delete_migration_credential_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delete_migration_credential_with_http_info: #{e}"
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


## delta_sync_migration

> <StartMigration202Response> delta_sync_migration(id)

Run a delta sync

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Run a delta sync
  result = api_instance.delta_sync_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delta_sync_migration: #{e}"
end
```

#### Using the delta_sync_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<StartMigration202Response>, Integer, Hash)> delta_sync_migration_with_http_info(id)

```ruby
begin
  # Run a delta sync
  data, status_code, headers = api_instance.delta_sync_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <StartMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->delta_sync_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## discover_migration

> <DiscoverMigration202Response> discover_migration(id)

Discover source mailboxes

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Discover source mailboxes
  result = api_instance.discover_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->discover_migration: #{e}"
end
```

#### Using the discover_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoverMigration202Response>, Integer, Hash)> discover_migration_with_http_info(id)

```ruby
begin
  # Discover source mailboxes
  data, status_code, headers = api_instance.discover_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoverMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->discover_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## final_sync_migration

> <StartMigration202Response> final_sync_migration(id)

Run the final sync before cutover

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Run the final sync before cutover
  result = api_instance.final_sync_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->final_sync_migration: #{e}"
end
```

#### Using the final_sync_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<StartMigration202Response>, Integer, Hash)> final_sync_migration_with_http_info(id)

```ruby
begin
  # Run the final sync before cutover
  data, status_code, headers = api_instance.final_sync_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <StartMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->final_sync_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_migration

> <Migration> get_migration(id)

Get a migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a migration
  result = api_instance.get_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->get_migration: #{e}"
end
```

#### Using the get_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Migration>, Integer, Hash)> get_migration_with_http_info(id)

```ruby
begin
  # Get a migration
  data, status_code, headers = api_instance.get_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Migration>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->get_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_migration_progress

> <MigrationProgress> get_migration_progress(id)

Get migration progress

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get migration progress
  result = api_instance.get_migration_progress(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->get_migration_progress: #{e}"
end
```

#### Using the get_migration_progress_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MigrationProgress>, Integer, Hash)> get_migration_progress_with_http_info(id)

```ruby
begin
  # Get migration progress
  data, status_code, headers = api_instance.get_migration_progress_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MigrationProgress>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->get_migration_progress_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**MigrationProgress**](MigrationProgress.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_migration_credentials

> <ListMigrationCredentials200Response> list_migration_credentials

List migration credentials

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new

begin
  # List migration credentials
  result = api_instance.list_migration_credentials
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_credentials: #{e}"
end
```

#### Using the list_migration_credentials_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMigrationCredentials200Response>, Integer, Hash)> list_migration_credentials_with_http_info

```ruby
begin
  # List migration credentials
  data, status_code, headers = api_instance.list_migration_credentials_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMigrationCredentials200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_credentials_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListMigrationCredentials200Response**](ListMigrationCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_migration_events

> <ListMigrationEvents200Response> list_migration_events(id)

List migration events

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # List migration events
  result = api_instance.list_migration_events(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_events: #{e}"
end
```

#### Using the list_migration_events_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMigrationEvents200Response>, Integer, Hash)> list_migration_events_with_http_info(id)

```ruby
begin
  # List migration events
  data, status_code, headers = api_instance.list_migration_events_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMigrationEvents200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_events_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**ListMigrationEvents200Response**](ListMigrationEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_migration_mailboxes

> <ListMigrationMailboxes200Response> list_migration_mailboxes(id)

List migration mailboxes

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # List migration mailboxes
  result = api_instance.list_migration_mailboxes(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_mailboxes: #{e}"
end
```

#### Using the list_migration_mailboxes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMigrationMailboxes200Response>, Integer, Hash)> list_migration_mailboxes_with_http_info(id)

```ruby
begin
  # List migration mailboxes
  data, status_code, headers = api_instance.list_migration_mailboxes_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMigrationMailboxes200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migration_mailboxes_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**ListMigrationMailboxes200Response**](ListMigrationMailboxes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_migrations

> <ListMigrations200Response> list_migrations

List migrations

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new

begin
  # List migrations
  result = api_instance.list_migrations
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migrations: #{e}"
end
```

#### Using the list_migrations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMigrations200Response>, Integer, Hash)> list_migrations_with_http_info

```ruby
begin
  # List migrations
  data, status_code, headers = api_instance.list_migrations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMigrations200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->list_migrations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListMigrations200Response**](ListMigrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## map_migration

> <DiscoverMigration202Response> map_migration(id, map_migration_request)

Map source to destination mailboxes

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
map_migration_request = Lockally::MapMigrationRequest.new({mappings: [Lockally::MapMigrationRequestMappingsInner.new({source_email: 'source_email_example', dest_email: 'dest_email_example'})]}) # MapMigrationRequest | 

begin
  # Map source to destination mailboxes
  result = api_instance.map_migration(id, map_migration_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->map_migration: #{e}"
end
```

#### Using the map_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoverMigration202Response>, Integer, Hash)> map_migration_with_http_info(id, map_migration_request)

```ruby
begin
  # Map source to destination mailboxes
  data, status_code, headers = api_instance.map_migration_with_http_info(id, map_migration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoverMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->map_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **map_migration_request** | [**MapMigrationRequest**](MapMigrationRequest.md) |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## retry_migration

> <DiscoverMigration202Response> retry_migration(id)

Retry a failed or cancelled migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Retry a failed or cancelled migration
  result = api_instance.retry_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->retry_migration: #{e}"
end
```

#### Using the retry_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoverMigration202Response>, Integer, Hash)> retry_migration_with_http_info(id)

```ruby
begin
  # Retry a failed or cancelled migration
  data, status_code, headers = api_instance.retry_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoverMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->retry_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## start_migration

> <StartMigration202Response> start_migration(id)

Start the migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Start the migration
  result = api_instance.start_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->start_migration: #{e}"
end
```

#### Using the start_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<StartMigration202Response>, Integer, Hash)> start_migration_with_http_info(id)

```ruby
begin
  # Start the migration
  data, status_code, headers = api_instance.start_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <StartMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->start_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_migration

> <Migration> update_migration(id, update_migration_request)

Update a migration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_migration_request = Lockally::UpdateMigrationRequest.new # UpdateMigrationRequest | 

begin
  # Update a migration
  result = api_instance.update_migration(id, update_migration_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->update_migration: #{e}"
end
```

#### Using the update_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Migration>, Integer, Hash)> update_migration_with_http_info(id, update_migration_request)

```ruby
begin
  # Update a migration
  data, status_code, headers = api_instance.update_migration_with_http_info(id, update_migration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Migration>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->update_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_migration_request** | [**UpdateMigrationRequest**](UpdateMigrationRequest.md) |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_migration_mailbox

> update_migration_mailbox(id, mbx_id, update_migration_mailbox_request)

Update a migration mailbox

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
mbx_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_migration_mailbox_request = Lockally::UpdateMigrationMailboxRequest.new # UpdateMigrationMailboxRequest | 

begin
  # Update a migration mailbox
  api_instance.update_migration_mailbox(id, mbx_id, update_migration_mailbox_request)
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->update_migration_mailbox: #{e}"
end
```

#### Using the update_migration_mailbox_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_migration_mailbox_with_http_info(id, mbx_id, update_migration_mailbox_request)

```ruby
begin
  # Update a migration mailbox
  data, status_code, headers = api_instance.update_migration_mailbox_with_http_info(id, mbx_id, update_migration_mailbox_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->update_migration_mailbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **mbx_id** | **String** |  |  |
| **update_migration_mailbox_request** | [**UpdateMigrationMailboxRequest**](UpdateMigrationMailboxRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json


## validate_migration

> <StartMigration202Response> validate_migration(id)

Validate migrated data

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MigrationsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Validate migrated data
  result = api_instance.validate_migration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->validate_migration: #{e}"
end
```

#### Using the validate_migration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<StartMigration202Response>, Integer, Hash)> validate_migration_with_http_info(id)

```ruby
begin
  # Validate migrated data
  data, status_code, headers = api_instance.validate_migration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <StartMigration202Response>
rescue Lockally::ApiError => e
  puts "Error when calling MigrationsApi->validate_migration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

