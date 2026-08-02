# Lockally::EncryptionApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**batch_lookup_public_keys**](EncryptionApi.md#batch_lookup_public_keys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email |
| [**create_encryption_key**](EncryptionApi.md#create_encryption_key) | **POST** /v1/encryption/keys | Upload an encryption key pair |
| [**create_encryption_recovery**](EncryptionApi.md#create_encryption_recovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob |
| [**get_encryption_key**](EncryptionApi.md#get_encryption_key) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox |
| [**rotate_encryption_key**](EncryptionApi.md#rotate_encryption_key) | **POST** /v1/encryption/keys/rotate | Rotate an encryption key |


## batch_lookup_public_keys

> <BatchLookupPublicKeys200Response> batch_lookup_public_keys(emails)

Batch-lookup public keys by email

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::EncryptionApi.new
emails = 'emails_example' # String | Comma-separated list of email addresses

begin
  # Batch-lookup public keys by email
  result = api_instance.batch_lookup_public_keys(emails)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->batch_lookup_public_keys: #{e}"
end
```

#### Using the batch_lookup_public_keys_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BatchLookupPublicKeys200Response>, Integer, Hash)> batch_lookup_public_keys_with_http_info(emails)

```ruby
begin
  # Batch-lookup public keys by email
  data, status_code, headers = api_instance.batch_lookup_public_keys_with_http_info(emails)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BatchLookupPublicKeys200Response>
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->batch_lookup_public_keys_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **emails** | **String** | Comma-separated list of email addresses |  |

### Return type

[**BatchLookupPublicKeys200Response**](BatchLookupPublicKeys200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## create_encryption_key

> <CreateEncryptionKey201Response> create_encryption_key(create_encryption_key_request)

Upload an encryption key pair

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::EncryptionApi.new
create_encryption_key_request = Lockally::CreateEncryptionKeyRequest.new({mailbox_email: 'mailbox_email_example', public_key: 'public_key_example', encrypted_private_key: 'encrypted_private_key_example'}) # CreateEncryptionKeyRequest | 

begin
  # Upload an encryption key pair
  result = api_instance.create_encryption_key(create_encryption_key_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->create_encryption_key: #{e}"
end
```

#### Using the create_encryption_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateEncryptionKey201Response>, Integer, Hash)> create_encryption_key_with_http_info(create_encryption_key_request)

```ruby
begin
  # Upload an encryption key pair
  data, status_code, headers = api_instance.create_encryption_key_with_http_info(create_encryption_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateEncryptionKey201Response>
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->create_encryption_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_encryption_key_request** | [**CreateEncryptionKeyRequest**](CreateEncryptionKeyRequest.md) |  |  |

### Return type

[**CreateEncryptionKey201Response**](CreateEncryptionKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_encryption_recovery

> create_encryption_recovery(create_encryption_recovery_request)

Store an encryption recovery blob

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::EncryptionApi.new
create_encryption_recovery_request = Lockally::CreateEncryptionRecoveryRequest.new({mailbox_email: 'mailbox_email_example', recovery_blob: 'recovery_blob_example'}) # CreateEncryptionRecoveryRequest | 

begin
  # Store an encryption recovery blob
  api_instance.create_encryption_recovery(create_encryption_recovery_request)
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->create_encryption_recovery: #{e}"
end
```

#### Using the create_encryption_recovery_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_encryption_recovery_with_http_info(create_encryption_recovery_request)

```ruby
begin
  # Store an encryption recovery blob
  data, status_code, headers = api_instance.create_encryption_recovery_with_http_info(create_encryption_recovery_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->create_encryption_recovery_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_encryption_recovery_request** | [**CreateEncryptionRecoveryRequest**](CreateEncryptionRecoveryRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json


## get_encryption_key

> <GetEncryptionKey200Response> get_encryption_key(email)

Get encryption key for a mailbox

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::EncryptionApi.new
email = 'email_example' # String | 

begin
  # Get encryption key for a mailbox
  result = api_instance.get_encryption_key(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->get_encryption_key: #{e}"
end
```

#### Using the get_encryption_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetEncryptionKey200Response>, Integer, Hash)> get_encryption_key_with_http_info(email)

```ruby
begin
  # Get encryption key for a mailbox
  data, status_code, headers = api_instance.get_encryption_key_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetEncryptionKey200Response>
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->get_encryption_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**GetEncryptionKey200Response**](GetEncryptionKey200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## rotate_encryption_key

> rotate_encryption_key(rotate_encryption_key_request)

Rotate an encryption key

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::EncryptionApi.new
rotate_encryption_key_request = Lockally::RotateEncryptionKeyRequest.new({mailbox_email: 'mailbox_email_example', encrypted_private_key: 'encrypted_private_key_example'}) # RotateEncryptionKeyRequest | 

begin
  # Rotate an encryption key
  api_instance.rotate_encryption_key(rotate_encryption_key_request)
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->rotate_encryption_key: #{e}"
end
```

#### Using the rotate_encryption_key_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> rotate_encryption_key_with_http_info(rotate_encryption_key_request)

```ruby
begin
  # Rotate an encryption key
  data, status_code, headers = api_instance.rotate_encryption_key_with_http_info(rotate_encryption_key_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->rotate_encryption_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rotate_encryption_key_request** | [**RotateEncryptionKeyRequest**](RotateEncryptionKeyRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json

