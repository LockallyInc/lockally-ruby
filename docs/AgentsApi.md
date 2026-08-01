# Lockally::AgentsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_api_keys_key_id_mailboxes_get**](AgentsApi.md#v1_api_keys_key_id_mailboxes_get) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key&#39;s mailbox grants |
| [**v1_api_keys_key_id_mailboxes_mailbox_id_delete**](AgentsApi.md#v1_api_keys_key_id_mailboxes_mailbox_id_delete) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant |
| [**v1_api_keys_key_id_mailboxes_post**](AgentsApi.md#v1_api_keys_key_id_mailboxes_post) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key |
| [**v1_auth_whoami_get**](AgentsApi.md#v1_auth_whoami_get) | **GET** /v1/auth/whoami | Introspect the calling credentials |
| [**v1_contacts_lookup_get**](AgentsApi.md#v1_contacts_lookup_get) | **GET** /v1/contacts/lookup | Who is this sender? |
| [**v1_inboxes_get**](AgentsApi.md#v1_inboxes_get) | **GET** /v1/inboxes | List granted inboxes |
| [**v1_inboxes_mailbox_messages_post**](AgentsApi.md#v1_inboxes_mailbox_messages_post) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream) |
| [**v1_inboxes_mailbox_threads_get**](AgentsApi.md#v1_inboxes_mailbox_threads_get) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads |
| [**v1_threads_thread_id_get**](AgentsApi.md#v1_threads_thread_id_get) | **GET** /v1/threads/{threadID} | Get a whole conversation |
| [**v1_threads_thread_id_messages_message_id_attachments_idx_get**](AgentsApi.md#v1_threads_thread_id_messages_message_id_attachments_idx_get) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment |
| [**v1_threads_thread_id_messages_message_id_get**](AgentsApi.md#v1_threads_thread_id_messages_message_id_get) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body |
| [**v1_threads_thread_id_messages_message_id_read_post**](AgentsApi.md#v1_threads_thread_id_messages_message_id_read_post) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread |
| [**v1_threads_thread_id_reply_post**](AgentsApi.md#v1_threads_thread_id_reply_post) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream) |


## v1_api_keys_key_id_mailboxes_get

> Object v1_api_keys_key_id_mailboxes_get(key_id)

List a key's mailbox grants

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
key_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # List a key's mailbox grants
  result = api_instance.v1_api_keys_key_id_mailboxes_get(key_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_get: #{e}"
end
```

#### Using the v1_api_keys_key_id_mailboxes_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_api_keys_key_id_mailboxes_get_with_http_info(key_id)

```ruby
begin
  # List a key's mailbox grants
  data, status_code, headers = api_instance.v1_api_keys_key_id_mailboxes_get_with_http_info(key_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_api_keys_key_id_mailboxes_mailbox_id_delete

> v1_api_keys_key_id_mailboxes_mailbox_id_delete(key_id, mailbox_id)

Revoke a mailbox grant

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
key_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
mailbox_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Revoke a mailbox grant
  api_instance.v1_api_keys_key_id_mailboxes_mailbox_id_delete(key_id, mailbox_id)
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_mailbox_id_delete: #{e}"
end
```

#### Using the v1_api_keys_key_id_mailboxes_mailbox_id_delete_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_api_keys_key_id_mailboxes_mailbox_id_delete_with_http_info(key_id, mailbox_id)

```ruby
begin
  # Revoke a mailbox grant
  data, status_code, headers = api_instance.v1_api_keys_key_id_mailboxes_mailbox_id_delete_with_http_info(key_id, mailbox_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_mailbox_id_delete_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key_id** | **String** |  |  |
| **mailbox_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## v1_api_keys_key_id_mailboxes_post

> Object v1_api_keys_key_id_mailboxes_post(key_id)

Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key — the server cannot read E2E mailboxes.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
key_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Grant a mailbox to a key
  result = api_instance.v1_api_keys_key_id_mailboxes_post(key_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_post: #{e}"
end
```

#### Using the v1_api_keys_key_id_mailboxes_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_api_keys_key_id_mailboxes_post_with_http_info(key_id)

```ruby
begin
  # Grant a mailbox to a key
  data, status_code, headers = api_instance.v1_api_keys_key_id_mailboxes_post_with_http_info(key_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_api_keys_key_id_mailboxes_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_auth_whoami_get

> Object v1_auth_whoami_get

Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new

begin
  # Introspect the calling credentials
  result = api_instance.v1_auth_whoami_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_auth_whoami_get: #{e}"
end
```

#### Using the v1_auth_whoami_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_auth_whoami_get_with_http_info

```ruby
begin
  # Introspect the calling credentials
  data, status_code, headers = api_instance.v1_auth_whoami_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_auth_whoami_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_contacts_lookup_get

> Object v1_contacts_lookup_get(email)

Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant's own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
email = 'email_example' # String | 

begin
  # Who is this sender?
  result = api_instance.v1_contacts_lookup_get(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_contacts_lookup_get: #{e}"
end
```

#### Using the v1_contacts_lookup_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_contacts_lookup_get_with_http_info(email)

```ruby
begin
  # Who is this sender?
  data, status_code, headers = api_instance.v1_contacts_lookup_get_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_contacts_lookup_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_inboxes_get

> Object v1_inboxes_get

List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new

begin
  # List granted inboxes
  result = api_instance.v1_inboxes_get
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_get: #{e}"
end
```

#### Using the v1_inboxes_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_inboxes_get_with_http_info

```ruby
begin
  # List granted inboxes
  data, status_code, headers = api_instance.v1_inboxes_get_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_get_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_inboxes_mailbox_messages_post

> Object v1_inboxes_mailbox_messages_post(mailbox, idempotency_key, v1_inboxes_mailbox_messages_post_request)

Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream=agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy=always_approve divert this into a pending draft.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
mailbox = 'mailbox_example' # String | 
idempotency_key = 'idempotency_key_example' # String | 
v1_inboxes_mailbox_messages_post_request = Lockally::V1InboxesMailboxMessagesPostRequest.new({to: ['to_example'], text: 'text_example'}) # V1InboxesMailboxMessagesPostRequest | 

begin
  # Start a new conversation (agent stream)
  result = api_instance.v1_inboxes_mailbox_messages_post(mailbox, idempotency_key, v1_inboxes_mailbox_messages_post_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_mailbox_messages_post: #{e}"
end
```

#### Using the v1_inboxes_mailbox_messages_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_inboxes_mailbox_messages_post_with_http_info(mailbox, idempotency_key, v1_inboxes_mailbox_messages_post_request)

```ruby
begin
  # Start a new conversation (agent stream)
  data, status_code, headers = api_instance.v1_inboxes_mailbox_messages_post_with_http_info(mailbox, idempotency_key, v1_inboxes_mailbox_messages_post_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_mailbox_messages_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox** | **String** |  |  |
| **idempotency_key** | **String** |  |  |
| **v1_inboxes_mailbox_messages_post_request** | [**V1InboxesMailboxMessagesPostRequest**](V1InboxesMailboxMessagesPostRequest.md) |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## v1_inboxes_mailbox_threads_get

> Object v1_inboxes_mailbox_threads_get(mailbox, opts)

List conversation threads

Newest-active first. Cursors: `?before=<RFC3339>` pages backwards; `?since=<RFC3339>` delta-syncs forward (oldest first) so an agent can catch up in order.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
mailbox = 'mailbox_example' # String | mailbox email or id
opts = {
  since: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  before: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  limit: 56 # Integer | 
}

begin
  # List conversation threads
  result = api_instance.v1_inboxes_mailbox_threads_get(mailbox, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_mailbox_threads_get: #{e}"
end
```

#### Using the v1_inboxes_mailbox_threads_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_inboxes_mailbox_threads_get_with_http_info(mailbox, opts)

```ruby
begin
  # List conversation threads
  data, status_code, headers = api_instance.v1_inboxes_mailbox_threads_get_with_http_info(mailbox, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_inboxes_mailbox_threads_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox** | **String** | mailbox email or id |  |
| **since** | **Time** |  | [optional] |
| **before** | **Time** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_get

> Object v1_threads_thread_id_get(thread_id)

Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a whole conversation
  result = api_instance.v1_threads_thread_id_get(thread_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_get: #{e}"
end
```

#### Using the v1_threads_thread_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_get_with_http_info(thread_id)

```ruby
begin
  # Get a whole conversation
  data, status_code, headers = api_instance.v1_threads_thread_id_get_with_http_info(thread_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_messages_message_id_attachments_idx_get

> v1_threads_thread_id_messages_message_id_attachments_idx_get(thread_id, message_id, idx)

Download an attachment

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
message_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
idx = 56 # Integer | 

begin
  # Download an attachment
  api_instance.v1_threads_thread_id_messages_message_id_attachments_idx_get(thread_id, message_id, idx)
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_attachments_idx_get: #{e}"
end
```

#### Using the v1_threads_thread_id_messages_message_id_attachments_idx_get_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> v1_threads_thread_id_messages_message_id_attachments_idx_get_with_http_info(thread_id, message_id, idx)

```ruby
begin
  # Download an attachment
  data, status_code, headers = api_instance.v1_threads_thread_id_messages_message_id_attachments_idx_get_with_http_info(thread_id, message_id, idx)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_attachments_idx_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **idx** | **Integer** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## v1_threads_thread_id_messages_message_id_get

> Object v1_threads_thread_id_messages_message_id_get(thread_id, message_id)

Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
message_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get one message with body
  result = api_instance.v1_threads_thread_id_messages_message_id_get(thread_id, message_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_get: #{e}"
end
```

#### Using the v1_threads_thread_id_messages_message_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_messages_message_id_get_with_http_info(thread_id, message_id)

```ruby
begin
  # Get one message with body
  data, status_code, headers = api_instance.v1_threads_thread_id_messages_message_id_get_with_http_info(thread_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_messages_message_id_read_post

> Object v1_threads_thread_id_messages_message_id_read_post(thread_id, message_id)

Mark read/unread

The ONLY way agent access changes unread state. Body: {\"read\": true|false} (default true).

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
message_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Mark read/unread
  result = api_instance.v1_threads_thread_id_messages_message_id_read_post(thread_id, message_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_read_post: #{e}"
end
```

#### Using the v1_threads_thread_id_messages_message_id_read_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_messages_message_id_read_post_with_http_info(thread_id, message_id)

```ruby
begin
  # Mark read/unread
  data, status_code, headers = api_instance.v1_threads_thread_id_messages_message_id_read_post_with_http_info(thread_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_messages_message_id_read_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_reply_post

> Object v1_threads_thread_id_reply_post(thread_id, idempotency_key)

Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation — a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::AgentsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
idempotency_key = 'idempotency_key_example' # String | 

begin
  # Reply in-thread (agent stream)
  result = api_instance.v1_threads_thread_id_reply_post(thread_id, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_reply_post: #{e}"
end
```

#### Using the v1_threads_thread_id_reply_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_reply_post_with_http_info(thread_id, idempotency_key)

```ruby
begin
  # Reply in-thread (agent stream)
  data, status_code, headers = api_instance.v1_threads_thread_id_reply_post_with_http_info(thread_id, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->v1_threads_thread_id_reply_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **idempotency_key** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

