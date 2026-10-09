# Lockally::DomainsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_domains_domain_delete**](DomainsApi.md#v1_domains_domain_delete) | **DELETE** /v1/domains/{domain} | Delete a domain |
| [**v1_domains_domain_get**](DomainsApi.md#v1_domains_domain_get) | **GET** /v1/domains/{domain} | Get a domain |
| [**v1_domains_domain_return_path_delete**](DomainsApi.md#v1_domains_domain_return_path_delete) | **DELETE** /v1/domains/{domain}/return-path | Turn off the custom Return-Path |
| [**v1_domains_domain_return_path_get**](DomainsApi.md#v1_domains_domain_return_path_get) | **GET** /v1/domains/{domain}/return-path | Get the custom Return-Path |
| [**v1_domains_domain_return_path_post**](DomainsApi.md#v1_domains_domain_return_path_post) | **POST** /v1/domains/{domain}/return-path | Turn on the custom Return-Path |
| [**v1_domains_domain_return_path_verify_post**](DomainsApi.md#v1_domains_domain_return_path_verify_post) | **POST** /v1/domains/{domain}/return-path/verify | Check the custom Return-Path records |
| [**v1_domains_domain_verify_post**](DomainsApi.md#v1_domains_domain_verify_post) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification |
| [**v1_domains_get**](DomainsApi.md#v1_domains_get) | **GET** /v1/domains | List domains |
| [**v1_domains_post**](DomainsApi.md#v1_domains_post) | **POST** /v1/domains | Register a domain |


## v1_domains_domain_delete

> v1_domains_domain_delete(domain)

Delete a domain

Removes the domain registration. Refuses with 409 if any mailbox is still attached — delete the mailboxes first. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Delete a domain
  api_instance.v1_domains_domain_delete(domain)
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_delete: #{e}"
end
```

#### Using the v1_domains_domain_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_domains_domain_delete_with_http_info(domain)

```ruby
begin
  # Delete a domain
  data, status_code, headers = api_instance.v1_domains_domain_delete_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_domains_domain_get

> <Domain> v1_domains_domain_get(domain)

Get a domain

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Get a domain
  result = api_instance.v1_domains_domain_get(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_get: #{e}"
end
```

#### Using the v1_domains_domain_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> v1_domains_domain_get_with_http_info(domain)

```ruby
begin
  # Get a domain
  data, status_code, headers = api_instance.v1_domains_domain_get_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_domain_return_path_delete

> v1_domains_domain_return_path_delete(domain)

Turn off the custom Return-Path

API mail uses the sender's own address as the envelope sender again, from the next message. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Turn off the custom Return-Path
  api_instance.v1_domains_domain_return_path_delete(domain)
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_delete: #{e}"
end
```

#### Using the v1_domains_domain_return_path_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_domains_domain_return_path_delete_with_http_info(domain)

```ruby
begin
  # Turn off the custom Return-Path
  data, status_code, headers = api_instance.v1_domains_domain_return_path_delete_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_domains_domain_return_path_get

> <ReturnPath> v1_domains_domain_return_path_get(domain)

Get the custom Return-Path

A custom Return-Path moves the envelope sender of mail sent through the API from this domain onto `bounces.<domain>`. Bounce reports then come back to Lockally instead of the sending mailbox, and a bounce that arrives after delivery marks the message bounced, suppresses the address and fires `delivery.bounced`. Mail sent from webmail or mail apps is not affected. DKIM stays signed by the domain itself. `status` is `off`, `pending` (records not confirmed yet) or `active`. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Get the custom Return-Path
  result = api_instance.v1_domains_domain_return_path_get(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_get: #{e}"
end
```

#### Using the v1_domains_domain_return_path_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> v1_domains_domain_return_path_get_with_http_info(domain)

```ruby
begin
  # Get the custom Return-Path
  data, status_code, headers = api_instance.v1_domains_domain_return_path_get_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_domain_return_path_post

> <ReturnPath> v1_domains_domain_return_path_post(domain)

Turn on the custom Return-Path

Moves it to `pending` and returns the two records to publish on `bounces.<domain>`. Nothing changes for mail until they are confirmed with the verify call. The domain must be verified. Available on every plan except Free. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Turn on the custom Return-Path
  result = api_instance.v1_domains_domain_return_path_post(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_post: #{e}"
end
```

#### Using the v1_domains_domain_return_path_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> v1_domains_domain_return_path_post_with_http_info(domain)

```ruby
begin
  # Turn on the custom Return-Path
  data, status_code, headers = api_instance.v1_domains_domain_return_path_post_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_domain_return_path_verify_post

> <ReturnPath> v1_domains_domain_return_path_verify_post(domain)

Check the custom Return-Path records

Looks up the MX and SPF records on `bounces.<domain>`. Returns 200 either way: while a record is missing the status stays `pending` and `check` says which one. Once both are found the Return-Path becomes `active` and the send path starts using it. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Check the custom Return-Path records
  result = api_instance.v1_domains_domain_return_path_verify_post(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_verify_post: #{e}"
end
```

#### Using the v1_domains_domain_return_path_verify_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> v1_domains_domain_return_path_verify_post_with_http_info(domain)

```ruby
begin
  # Check the custom Return-Path records
  data, status_code, headers = api_instance.v1_domains_domain_return_path_verify_post_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_return_path_verify_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_domain_verify_post

> <Domain> v1_domains_domain_verify_post(domain)

Force-poll DNS verification

Synchronously checks the `_lockally-verify.<domain>` TXT record against the stored verification token. Returns 200 either way: the returned `verified` boolean tells you whether DNS now confirms. Caller polls until `verified: true`. In v2 a background worker auto-polls and fires a `domain.verified` webhook. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
domain = 'domain_example' # String | 

begin
  # Force-poll DNS verification
  result = api_instance.v1_domains_domain_verify_post(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_verify_post: #{e}"
end
```

#### Using the v1_domains_domain_verify_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> v1_domains_domain_verify_post_with_http_info(domain)

```ruby
begin
  # Force-poll DNS verification
  data, status_code, headers = api_instance.v1_domains_domain_verify_post_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_domain_verify_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_get

> <V1DomainsGet200Response> v1_domains_get

List domains

Returns every domain registered under the calling tenant.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new

begin
  # List domains
  result = api_instance.v1_domains_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_get: #{e}"
end
```

#### Using the v1_domains_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1DomainsGet200Response>, Integer, Hash)> v1_domains_get_with_http_info

```ruby
begin
  # List domains
  data, status_code, headers = api_instance.v1_domains_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1DomainsGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DomainsGet200Response**](V1DomainsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_domains_post

> <Domain> v1_domains_post(v1_domains_post_request)

Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to `mx1`/`mx2.lockally.com`, DMARC seed).  **Idempotent** — re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant's published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DomainsApi.new
v1_domains_post_request = Lockally::V1DomainsPostRequest.new({domain: 'acme.com'}) # V1DomainsPostRequest | 

begin
  # Register a domain
  result = api_instance.v1_domains_post(v1_domains_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_post: #{e}"
end
```

#### Using the v1_domains_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> v1_domains_post_with_http_info(v1_domains_post_request)

```ruby
begin
  # Register a domain
  data, status_code, headers = api_instance.v1_domains_post_with_http_info(v1_domains_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->v1_domains_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_domains_post_request** | [**V1DomainsPostRequest**](V1DomainsPostRequest.md) |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

