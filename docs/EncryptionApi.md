# Lockally::EncryptionApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**batch_lookup_public_keys**](EncryptionApi.md#batch_lookup_public_keys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email |
| [**create_encryption_key**](EncryptionApi.md#create_encryption_key) | **POST** /v1/encryption/keys | Upload an encryption key pair |
| [**create_encryption_recovery**](EncryptionApi.md#create_encryption_recovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob |
| [**get_encryption_key**](EncryptionApi.md#get_encryption_key) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox |
| [**get_encryption_status**](EncryptionApi.md#get_encryption_status) | **GET** /v1/encryption/status | End-to-end encryption status for the workspace |
| [**rotate_encryption_key**](EncryptionApi.md#rotate_encryption_key) | **POST** /v1/encryption/keys/rotate | Re-seal an encryption key under a new password |


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

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. A mailbox that already has a key is starting over: the old key is kept inactive, not destroyed, and the new one starts without a recovery code.

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
create_encryption_key_request = Lockally::CreateEncryptionKeyRequest.new({public_key: 'public_key_example', encrypted_private_key: 'encrypted_private_key_example'}) # CreateEncryptionKeyRequest | 

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

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. The blob is the private key sealed under a recovery code the browser generated; the code itself is never sent. Replaces any earlier one.

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
create_encryption_recovery_request = Lockally::CreateEncryptionRecoveryRequest.new({recovery_blob: 'recovery_blob_example'}) # CreateEncryptionRecoveryRequest | 

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

Anyone in the workspace gets the public key. The mailbox's own webmail session also gets its sealed private key, its sealed recovery copy and the recovery state.

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


## get_encryption_status

> <GetEncryptionStatus200Response> get_encryption_status

End-to-end encryption status for the workspace

For administrators: whether the add-on is on, and for each mailbox whether it has a key and a recovery code. Carries no key material.

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

begin
  # End-to-end encryption status for the workspace
  result = api_instance.get_encryption_status
  p result
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->get_encryption_status: #{e}"
end
```

#### Using the get_encryption_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetEncryptionStatus200Response>, Integer, Hash)> get_encryption_status_with_http_info

```ruby
begin
  # End-to-end encryption status for the workspace
  data, status_code, headers = api_instance.get_encryption_status_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetEncryptionStatus200Response>
rescue Lockally::ApiError => e
  puts "Error when calling EncryptionApi->get_encryption_status_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetEncryptionStatus200Response**](GetEncryptionStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## rotate_encryption_key

> rotate_encryption_key(rotate_encryption_key_request)

Re-seal an encryption key under a new password

Only the mailbox's own webmail session may call this; an API key is refused with 403. The private key is sealed under that mailbox's password, which an administrator never has. `mailbox_email`, if sent, must be the caller's own mailbox. The key pair does not change, so every message stays readable.

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
rotate_encryption_key_request = Lockally::RotateEncryptionKeyRequest.new({encrypted_private_key: 'encrypted_private_key_example'}) # RotateEncryptionKeyRequest | 

begin
  # Re-seal an encryption key under a new password
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
  # Re-seal an encryption key under a new password
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

