# Lockally::DomainsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_domain**](DomainsApi.md#create_domain) | **POST** /v1/domains | Register a domain |
| [**delete_domain**](DomainsApi.md#delete_domain) | **DELETE** /v1/domains/{domain} | Delete a domain |
| [**disable_return_path**](DomainsApi.md#disable_return_path) | **DELETE** /v1/domains/{domain}/return-path | Turn off the custom Return-Path |
| [**enable_return_path**](DomainsApi.md#enable_return_path) | **POST** /v1/domains/{domain}/return-path | Turn on the custom Return-Path |
| [**get_domain**](DomainsApi.md#get_domain) | **GET** /v1/domains/{domain} | Get a domain |
| [**get_return_path**](DomainsApi.md#get_return_path) | **GET** /v1/domains/{domain}/return-path | Get the custom Return-Path |
| [**list_domains**](DomainsApi.md#list_domains) | **GET** /v1/domains | List domains |
| [**verify_domain**](DomainsApi.md#verify_domain) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification |
| [**verify_return_path**](DomainsApi.md#verify_return_path) | **POST** /v1/domains/{domain}/return-path/verify | Check the custom Return-Path records |


## create_domain

> <Domain> create_domain(create_domain_request)

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
create_domain_request = Lockally::CreateDomainRequest.new({domain: 'acme.com'}) # CreateDomainRequest | 

begin
  # Register a domain
  result = api_instance.create_domain(create_domain_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->create_domain: #{e}"
end
```

#### Using the create_domain_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> create_domain_with_http_info(create_domain_request)

```ruby
begin
  # Register a domain
  data, status_code, headers = api_instance.create_domain_with_http_info(create_domain_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->create_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_domain_request** | [**CreateDomainRequest**](CreateDomainRequest.md) |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_domain

> delete_domain(domain)

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
  api_instance.delete_domain(domain)
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->delete_domain: #{e}"
end
```

#### Using the delete_domain_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_domain_with_http_info(domain)

```ruby
begin
  # Delete a domain
  data, status_code, headers = api_instance.delete_domain_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->delete_domain_with_http_info: #{e}"
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


## disable_return_path

> disable_return_path(domain)

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
  api_instance.disable_return_path(domain)
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->disable_return_path: #{e}"
end
```

#### Using the disable_return_path_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> disable_return_path_with_http_info(domain)

```ruby
begin
  # Turn off the custom Return-Path
  data, status_code, headers = api_instance.disable_return_path_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->disable_return_path_with_http_info: #{e}"
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


## enable_return_path

> <ReturnPath> enable_return_path(domain)

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
  result = api_instance.enable_return_path(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->enable_return_path: #{e}"
end
```

#### Using the enable_return_path_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> enable_return_path_with_http_info(domain)

```ruby
begin
  # Turn on the custom Return-Path
  data, status_code, headers = api_instance.enable_return_path_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->enable_return_path_with_http_info: #{e}"
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


## get_domain

> <Domain> get_domain(domain)

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
  result = api_instance.get_domain(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->get_domain: #{e}"
end
```

#### Using the get_domain_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> get_domain_with_http_info(domain)

```ruby
begin
  # Get a domain
  data, status_code, headers = api_instance.get_domain_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->get_domain_with_http_info: #{e}"
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


## get_return_path

> <ReturnPath> get_return_path(domain)

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
  result = api_instance.get_return_path(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->get_return_path: #{e}"
end
```

#### Using the get_return_path_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> get_return_path_with_http_info(domain)

```ruby
begin
  # Get the custom Return-Path
  data, status_code, headers = api_instance.get_return_path_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->get_return_path_with_http_info: #{e}"
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


## list_domains

> <ListDomains200Response> list_domains

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
  result = api_instance.list_domains
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->list_domains: #{e}"
end
```

#### Using the list_domains_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListDomains200Response>, Integer, Hash)> list_domains_with_http_info

```ruby
begin
  # List domains
  data, status_code, headers = api_instance.list_domains_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListDomains200Response>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->list_domains_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListDomains200Response**](ListDomains200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## verify_domain

> <Domain> verify_domain(domain)

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
  result = api_instance.verify_domain(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->verify_domain: #{e}"
end
```

#### Using the verify_domain_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Domain>, Integer, Hash)> verify_domain_with_http_info(domain)

```ruby
begin
  # Force-poll DNS verification
  data, status_code, headers = api_instance.verify_domain_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Domain>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->verify_domain_with_http_info: #{e}"
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


## verify_return_path

> <ReturnPath> verify_return_path(domain)

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
  result = api_instance.verify_return_path(domain)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->verify_return_path: #{e}"
end
```

#### Using the verify_return_path_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ReturnPath>, Integer, Hash)> verify_return_path_with_http_info(domain)

```ruby
begin
  # Check the custom Return-Path records
  data, status_code, headers = api_instance.verify_return_path_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ReturnPath>
rescue Lockally::ApiError => e
  puts "Error when calling DomainsApi->verify_return_path_with_http_info: #{e}"
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

