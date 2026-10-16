# Lockally::MailboxesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_shared_member**](MailboxesApi.md#add_shared_member) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member |
| [**create_mailbox**](MailboxesApi.md#create_mailbox) | **POST** /v1/mailboxes | Create a mailbox |
| [**delete_mailbox**](MailboxesApi.md#delete_mailbox) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox |
| [**delete_vacation_responder**](MailboxesApi.md#delete_vacation_responder) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder |
| [**download_mailbox_export**](MailboxesApi.md#download_mailbox_export) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export |
| [**export_mailbox**](MailboxesApi.md#export_mailbox) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export |
| [**get_mailbox**](MailboxesApi.md#get_mailbox) | **GET** /v1/mailboxes/{email} | Get a mailbox |
| [**get_vacation_responder**](MailboxesApi.md#get_vacation_responder) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder |
| [**list_mailboxes**](MailboxesApi.md#list_mailboxes) | **GET** /v1/mailboxes | List mailboxes |
| [**list_shared_members**](MailboxesApi.md#list_shared_members) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members |
| [**list_vacation_responders**](MailboxesApi.md#list_vacation_responders) | **GET** /v1/vacation | List all vacation responders |
| [**remove_shared_member**](MailboxesApi.md#remove_shared_member) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member |
| [**set_vacation_responder**](MailboxesApi.md#set_vacation_responder) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder |
| [**update_mailbox**](MailboxesApi.md#update_mailbox) | **PATCH** /v1/mailboxes/{email} | Update a mailbox |


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


## create_mailbox

> <Mailbox> create_mailbox(create_mailbox_request)

Create a mailbox

Creates a mailbox on a tenant-verified domain. If `password` is omitted, lockally generates a 16-char password and returns it in the response, shown once.  **Gate.** The mailbox's domain must already be registered AND verified for this tenant (via `/v1/domains` + `/v1/domains/{domain}/verify`).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED, password is NOT regenerated. To change a password, use PATCH instead. 

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
create_mailbox_request = Lockally::CreateMailboxRequest.new({email: 'alice@acme.com'}) # CreateMailboxRequest | 

begin
  # Create a mailbox
  result = api_instance.create_mailbox(create_mailbox_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->create_mailbox: #{e}"
end
```

#### Using the create_mailbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> create_mailbox_with_http_info(create_mailbox_request)

```ruby
begin
  # Create a mailbox
  data, status_code, headers = api_instance.create_mailbox_with_http_info(create_mailbox_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->create_mailbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_mailbox_request** | [**CreateMailboxRequest**](CreateMailboxRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_mailbox

> delete_mailbox(email)

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
  api_instance.delete_mailbox(email)
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->delete_mailbox: #{e}"
end
```

#### Using the delete_mailbox_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_mailbox_with_http_info(email)

```ruby
begin
  # Soft-delete a mailbox
  data, status_code, headers = api_instance.delete_mailbox_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->delete_mailbox_with_http_info: #{e}"
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


## delete_vacation_responder

> delete_vacation_responder(email)

Remove the vacation responder

Idempotent, 204 whether or not a row existed.

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
  api_instance.delete_vacation_responder(email)
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->delete_vacation_responder: #{e}"
end
```

#### Using the delete_vacation_responder_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_vacation_responder_with_http_info(email)

```ruby
begin
  # Remove the vacation responder
  data, status_code, headers = api_instance.delete_vacation_responder_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->delete_vacation_responder_with_http_info: #{e}"
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


## download_mailbox_export

> File download_mailbox_export(email, token)

Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404, tokens are single-use. 

### Examples

```ruby
require 'time'
require 'lockally'

api_instance = Lockally::MailboxesApi.new
email = 'email_example' # String | 
token = 'token_example' # String | 

begin
  # Download a previously-issued mailbox export
  result = api_instance.download_mailbox_export(email, token)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->download_mailbox_export: #{e}"
end
```

#### Using the download_mailbox_export_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> download_mailbox_export_with_http_info(email, token)

```ruby
begin
  # Download a previously-issued mailbox export
  data, status_code, headers = api_instance.download_mailbox_export_with_http_info(email, token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->download_mailbox_export_with_http_info: #{e}"
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


## export_mailbox

> <ExportMailbox201Response> export_mailbox(email)

Request a mailbox export

Issues a one-shot \"presigned\" download URL for the mailbox's content in mbox format. The URL works without an Authorization header, the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (sent mail only). A later version will cover received mail for full inbox + folder structure + flags. The endpoint contract stays unchanged.  **Scope changed:** this used to accept `mailboxes:read`. It takes any mailbox in the tenant and returns that mailbox's mail, so it now requires `tenant:admin`, matching `POST /v1/ediscovery/export`. A key scoped `mailboxes:read` gets 403 and has to be reissued; admin console sessions are unaffected. 

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
  result = api_instance.export_mailbox(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->export_mailbox: #{e}"
end
```

#### Using the export_mailbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportMailbox201Response>, Integer, Hash)> export_mailbox_with_http_info(email)

```ruby
begin
  # Request a mailbox export
  data, status_code, headers = api_instance.export_mailbox_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportMailbox201Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->export_mailbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**ExportMailbox201Response**](ExportMailbox201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_mailbox

> <Mailbox> get_mailbox(email)

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
  result = api_instance.get_mailbox(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->get_mailbox: #{e}"
end
```

#### Using the get_mailbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> get_mailbox_with_http_info(email)

```ruby
begin
  # Get a mailbox
  data, status_code, headers = api_instance.get_mailbox_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->get_mailbox_with_http_info: #{e}"
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


## get_vacation_responder

> <VacationResponder> get_vacation_responder(email)

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
  result = api_instance.get_vacation_responder(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->get_vacation_responder: #{e}"
end
```

#### Using the get_vacation_responder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VacationResponder>, Integer, Hash)> get_vacation_responder_with_http_info(email)

```ruby
begin
  # Get the vacation responder
  data, status_code, headers = api_instance.get_vacation_responder_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VacationResponder>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->get_vacation_responder_with_http_info: #{e}"
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


## list_mailboxes

> <ListMailboxes200Response> list_mailboxes(opts)

List mailboxes

Returns mailboxes under the calling tenant, active and soft-deleted. `?limit=N` between 1 and 200 (default 50). 

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
  result = api_instance.list_mailboxes(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_mailboxes: #{e}"
end
```

#### Using the list_mailboxes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMailboxes200Response>, Integer, Hash)> list_mailboxes_with_http_info(opts)

```ruby
begin
  # List mailboxes
  data, status_code, headers = api_instance.list_mailboxes_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMailboxes200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_mailboxes_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**ListMailboxes200Response**](ListMailboxes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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


## list_vacation_responders

> <ListVacationResponders200Response> list_vacation_responders

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
  result = api_instance.list_vacation_responders
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_vacation_responders: #{e}"
end
```

#### Using the list_vacation_responders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListVacationResponders200Response>, Integer, Hash)> list_vacation_responders_with_http_info

```ruby
begin
  # List all vacation responders
  data, status_code, headers = api_instance.list_vacation_responders_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListVacationResponders200Response>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->list_vacation_responders_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListVacationResponders200Response**](ListVacationResponders200Response.md)

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


## set_vacation_responder

> <VacationResponder> set_vacation_responder(email, set_vacation_responder_request)

Set the vacation responder

Upsert, same endpoint creates or replaces the rule. Clears `synced_at`; the rule is staged until a later sync pushes it to the mail server. 

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
set_vacation_responder_request = Lockally::SetVacationResponderRequest.new({params: Lockally::VacationParams.new({subject: 'Out of office until June 5', body: 'Hi! I'm away until June 5. For urgent matters please contact ...'})}) # SetVacationResponderRequest | 

begin
  # Set the vacation responder
  result = api_instance.set_vacation_responder(email, set_vacation_responder_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->set_vacation_responder: #{e}"
end
```

#### Using the set_vacation_responder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VacationResponder>, Integer, Hash)> set_vacation_responder_with_http_info(email, set_vacation_responder_request)

```ruby
begin
  # Set the vacation responder
  data, status_code, headers = api_instance.set_vacation_responder_with_http_info(email, set_vacation_responder_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VacationResponder>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->set_vacation_responder_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **set_vacation_responder_request** | [**SetVacationResponderRequest**](SetVacationResponderRequest.md) |  |  |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_mailbox

> <Mailbox> update_mailbox(email, update_mailbox_request)

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
update_mailbox_request = Lockally::UpdateMailboxRequest.new # UpdateMailboxRequest | 

begin
  # Update a mailbox
  result = api_instance.update_mailbox(email, update_mailbox_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->update_mailbox: #{e}"
end
```

#### Using the update_mailbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Mailbox>, Integer, Hash)> update_mailbox_with_http_info(email, update_mailbox_request)

```ruby
begin
  # Update a mailbox
  data, status_code, headers = api_instance.update_mailbox_with_http_info(email, update_mailbox_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Mailbox>
rescue Lockally::ApiError => e
  puts "Error when calling MailboxesApi->update_mailbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **update_mailbox_request** | [**UpdateMailboxRequest**](UpdateMailboxRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

