# Lockally::MailboxesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_shared_member**](MailboxesApi.md#add_shared_member) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member |
| [**list_shared_members**](MailboxesApi.md#list_shared_members) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members |
| [**remove_shared_member**](MailboxesApi.md#remove_shared_member) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member |
| [**v1_mailboxes_email_delete**](MailboxesApi.md#v1_mailboxes_email_delete) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox |
| [**v1_mailboxes_email_export_download_get**](MailboxesApi.md#v1_mailboxes_email_export_download_get) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export |
| [**v1_mailboxes_email_export_post**](MailboxesApi.md#v1_mailboxes_email_export_post) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export |
| [**v1_mailboxes_email_get**](MailboxesApi.md#v1_mailboxes_email_get) | **GET** /v1/mailboxes/{email} | Get a mailbox |
| [**v1_mailboxes_email_patch**](MailboxesApi.md#v1_mailboxes_email_patch) | **PATCH** /v1/mailboxes/{email} | Update a mailbox |
| [**v1_mailboxes_email_vacation_delete**](MailboxesApi.md#v1_mailboxes_email_vacation_delete) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder |
| [**v1_mailboxes_email_vacation_get**](MailboxesApi.md#v1_mailboxes_email_vacation_get) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder |
| [**v1_mailboxes_email_vacation_put**](MailboxesApi.md#v1_mailboxes_email_vacation_put) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder |
| [**v1_mailboxes_get**](MailboxesApi.md#v1_mailboxes_get) | **GET** /v1/mailboxes | List mailboxes |
| [**v1_mailboxes_post**](MailboxesApi.md#v1_mailboxes_post) | **POST** /v1/mailboxes | Create a mailbox |
| [**v1_vacation_get**](MailboxesApi.md#v1_vacation_get) | **GET** /v1/vacation | List all vacation responders |


## add_shared_member

> <SharedMember> add_shared_member(email, add_shared_member_request)

Add a shared mailbox member

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
add_shared_member_request = Lockally::AddSharedMemberRequest.new({member_email: 'member_email_example'}) # AddSharedMemberRequest | 

begin
  # Add a shared mailbox member
  result = api_instance.add_shared_member(email, add_shared_member_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->add_shared_member: #{e}"
end
```

#### Using the add_shared_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SharedMember>, Integer, Hash)> add_shared_member_with_http_info(email, add_shared_member_request)

```ruby
begin
  # Add a shared mailbox member
  data, status_code, headers = api_instance.add_shared_member_with_http_info(email, add_shared_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SharedMember>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->add_shared_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **add_shared_member_request** | [**AddSharedMemberRequest**](AddSharedMemberRequest.md) |  |  |

### Return type

[**SharedMember**](SharedMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## list_shared_members

> <ListSharedMembers200Response> list_shared_members(email)

List shared mailbox members

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # List shared mailbox members
  result = api_instance.list_shared_members(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_shared_members: #{e}"
end
```

#### Using the list_shared_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListSharedMembers200Response>, Integer, Hash)> list_shared_members_with_http_info(email)

```ruby
begin
  # List shared mailbox members
  data, status_code, headers = api_instance.list_shared_members_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListSharedMembers200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_shared_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**ListSharedMembers200Response**](ListSharedMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## remove_shared_member

> remove_shared_member(email, member_email)

Remove a shared mailbox member

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
member_email = 'member_email_example' # String | 

begin
  # Remove a shared mailbox member
  api_instance.remove_shared_member(email, member_email)
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->remove_shared_member: #{e}"
end
```

#### Using the remove_shared_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_shared_member_with_http_info(email, member_email)

```ruby
begin
  # Remove a shared mailbox member
  data, status_code, headers = api_instance.remove_shared_member_with_http_info(email, member_email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->remove_shared_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **member_email** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_mailboxes_email_delete

> v1_mailboxes_email_delete(email)

Soft-delete a mailbox

Sets `soft_deleted_at = now()` and `hard_delete_after = now() + 90d` per design D25. A background sweep (planned) will hard-delete after the window. The mailbox is also disabled immediately. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # Soft-delete a mailbox
  api_instance.v1_mailboxes_email_delete(email)
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_delete: #{e}"
end
```

#### Using the v1_mailboxes_email_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_mailboxes_email_delete_with_http_info(email)

```ruby
begin
  # Soft-delete a mailbox
  data, status_code, headers = api_instance.v1_mailboxes_email_delete_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_mailboxes_email_export_download_get

> File v1_mailboxes_email_export_download_get(email, token)

Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404 — tokens are single-use. 

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
token = 'token_example' # String | 

begin
  # Download a previously-issued mailbox export
  result = api_instance.v1_mailboxes_email_export_download_get(email, token)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_export_download_get: #{e}"
end
```

#### Using the v1_mailboxes_email_export_download_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> v1_mailboxes_email_export_download_get_with_http_info(email, token)

```ruby
begin
  # Download a previously-issued mailbox export
  data, status_code, headers = api_instance.v1_mailboxes_email_export_download_get_with_http_info(email, token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_export_download_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **token** | **String** |  |  |

### Return type

**File**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/mbox, application/problem+json


## v1_mailboxes_email_export_post

> <V1MailboxesEmailExportPost201Response> v1_mailboxes_email_export_post(email)

Request a mailbox export

Issues a one-shot \"presigned\" download URL for the mailbox's content in mbox format. The URL works without an Authorization header — the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (from `lockally.messages`). v2 swaps in Stalwart's export primitive for full inbox + folder structure + flags. The endpoint contract stays unchanged. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # Request a mailbox export
  result = api_instance.v1_mailboxes_email_export_post(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_export_post: #{e}"
end
```

#### Using the v1_mailboxes_email_export_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1MailboxesEmailExportPost201Response>, Integer, Hash)> v1_mailboxes_email_export_post_with_http_info(email)

```ruby
begin
  # Request a mailbox export
  data, status_code, headers = api_instance.v1_mailboxes_email_export_post_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1MailboxesEmailExportPost201Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_export_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**V1MailboxesEmailExportPost201Response**](V1MailboxesEmailExportPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_mailboxes_email_get

> <Mailbox> v1_mailboxes_email_get(email)

Get a mailbox

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # Get a mailbox
  result = api_instance.v1_mailboxes_email_get(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_get: #{e}"
end
```

#### Using the v1_mailboxes_email_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> v1_mailboxes_email_get_with_http_info(email)

```ruby
begin
  # Get a mailbox
  data, status_code, headers = api_instance.v1_mailboxes_email_get_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_mailboxes_email_patch

> <Mailbox> v1_mailboxes_email_patch(email, v1_mailboxes_email_patch_request)

Update a mailbox

Supply at least one of `password`, `quota_bytes`, `disabled`. Returns the updated mailbox. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
v1_mailboxes_email_patch_request = Lockally::V1MailboxesEmailPatchRequest.new # V1MailboxesEmailPatchRequest | 

begin
  # Update a mailbox
  result = api_instance.v1_mailboxes_email_patch(email, v1_mailboxes_email_patch_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_patch: #{e}"
end
```

#### Using the v1_mailboxes_email_patch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> v1_mailboxes_email_patch_with_http_info(email, v1_mailboxes_email_patch_request)

```ruby
begin
  # Update a mailbox
  data, status_code, headers = api_instance.v1_mailboxes_email_patch_with_http_info(email, v1_mailboxes_email_patch_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_patch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **v1_mailboxes_email_patch_request** | [**V1MailboxesEmailPatchRequest**](V1MailboxesEmailPatchRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_mailboxes_email_vacation_delete

> v1_mailboxes_email_vacation_delete(email)

Remove the vacation responder

Idempotent — 204 whether or not a row existed.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # Remove the vacation responder
  api_instance.v1_mailboxes_email_vacation_delete(email)
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_delete: #{e}"
end
```

#### Using the v1_mailboxes_email_vacation_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_mailboxes_email_vacation_delete_with_http_info(email)

```ruby
begin
  # Remove the vacation responder
  data, status_code, headers = api_instance.v1_mailboxes_email_vacation_delete_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## v1_mailboxes_email_vacation_get

> <VacationResponder> v1_mailboxes_email_vacation_get(email)

Get the vacation responder

Returns the stored vacation rule or 404 if none is set.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 

begin
  # Get the vacation responder
  result = api_instance.v1_mailboxes_email_vacation_get(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_get: #{e}"
end
```

#### Using the v1_mailboxes_email_vacation_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VacationResponder>, Integer, Hash)> v1_mailboxes_email_vacation_get_with_http_info(email)

```ruby
begin
  # Get the vacation responder
  data, status_code, headers = api_instance.v1_mailboxes_email_vacation_get_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VacationResponder>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_mailboxes_email_vacation_put

> <VacationResponder> v1_mailboxes_email_vacation_put(email, v1_mailboxes_email_vacation_put_request)

Set the vacation responder

Upsert — same endpoint creates or replaces the rule. Clears `synced_at`; the rule is staged on lockally until a sync worker pushes it to the mail server. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
v1_mailboxes_email_vacation_put_request = Lockally::V1MailboxesEmailVacationPutRequest.new({params: Lockally::VacationParams.new({subject: 'Out of office until June 5', body: 'Hi! I'm away until June 5. For urgent matters please contact ...'})}) # V1MailboxesEmailVacationPutRequest | 

begin
  # Set the vacation responder
  result = api_instance.v1_mailboxes_email_vacation_put(email, v1_mailboxes_email_vacation_put_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_put: #{e}"
end
```

#### Using the v1_mailboxes_email_vacation_put_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VacationResponder>, Integer, Hash)> v1_mailboxes_email_vacation_put_with_http_info(email, v1_mailboxes_email_vacation_put_request)

```ruby
begin
  # Set the vacation responder
  data, status_code, headers = api_instance.v1_mailboxes_email_vacation_put_with_http_info(email, v1_mailboxes_email_vacation_put_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VacationResponder>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_email_vacation_put_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **v1_mailboxes_email_vacation_put_request** | [**V1MailboxesEmailVacationPutRequest**](V1MailboxesEmailVacationPutRequest.md) |  |  |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_mailboxes_get

> <V1MailboxesGet200Response> v1_mailboxes_get(opts)

List mailboxes

Returns mailboxes under the calling tenant — active and soft-deleted. `?limit=N` between 1 and 200 (default 50). 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
opts = {
  limit: 56 # Integer | 
}

begin
  # List mailboxes
  result = api_instance.v1_mailboxes_get(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_get: #{e}"
end
```

#### Using the v1_mailboxes_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1MailboxesGet200Response>, Integer, Hash)> v1_mailboxes_get_with_http_info(opts)

```ruby
begin
  # List mailboxes
  data, status_code, headers = api_instance.v1_mailboxes_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1MailboxesGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**V1MailboxesGet200Response**](V1MailboxesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## v1_mailboxes_post

> <Mailbox> v1_mailboxes_post(v1_mailboxes_post_request)

Create a mailbox

Creates a mailbox on a tenant-verified domain. If `password` is omitted, lockally generates a 16-char password and returns it in the response — shown once.  **Gate.** The mailbox's domain must already be registered AND verified for this tenant (via `/v1/domains` + `/v1/domains/{domain}/verify`).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED — password is NOT regenerated. To change a password, use PATCH instead. 

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new
v1_mailboxes_post_request = Lockally::V1MailboxesPostRequest.new({email: 'alice@acme.com'}) # V1MailboxesPostRequest | 

begin
  # Create a mailbox
  result = api_instance.v1_mailboxes_post(v1_mailboxes_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_post: #{e}"
end
```

#### Using the v1_mailboxes_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> v1_mailboxes_post_with_http_info(v1_mailboxes_post_request)

```ruby
begin
  # Create a mailbox
  data, status_code, headers = api_instance.v1_mailboxes_post_with_http_info(v1_mailboxes_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_mailboxes_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **v1_mailboxes_post_request** | [**V1MailboxesPostRequest**](V1MailboxesPostRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## v1_vacation_get

> <V1VacationGet200Response> v1_vacation_get

List all vacation responders

Returns every vacation responder for the calling tenant.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::MailboxesApi.new

begin
  # List all vacation responders
  result = api_instance.v1_vacation_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_vacation_get: #{e}"
end
```

#### Using the v1_vacation_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<V1VacationGet200Response>, Integer, Hash)> v1_vacation_get_with_http_info

```ruby
begin
  # List all vacation responders
  data, status_code, headers = api_instance.v1_vacation_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <V1VacationGet200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->v1_vacation_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1VacationGet200Response**](V1VacationGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json

