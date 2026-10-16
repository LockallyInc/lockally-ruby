# Lockally::AgentsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**download_thread_attachment**](AgentsApi.md#download_thread_attachment) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment |
| [**get_thread**](AgentsApi.md#get_thread) | **GET** /v1/threads/{threadID} | Get a whole conversation |
| [**get_thread_message**](AgentsApi.md#get_thread_message) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body |
| [**grant_api_key_mailbox**](AgentsApi.md#grant_api_key_mailbox) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key |
| [**list_api_key_mailboxes**](AgentsApi.md#list_api_key_mailboxes) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key&#39;s mailbox grants |
| [**list_inboxes**](AgentsApi.md#list_inboxes) | **GET** /v1/inboxes | List granted inboxes |
| [**list_threads**](AgentsApi.md#list_threads) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads |
| [**lookup_contact**](AgentsApi.md#lookup_contact) | **GET** /v1/contacts/lookup | Who is this sender? |
| [**mark_thread_message_read**](AgentsApi.md#mark_thread_message_read) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread |
| [**reply_to_thread**](AgentsApi.md#reply_to_thread) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream) |
| [**revoke_api_key_mailbox**](AgentsApi.md#revoke_api_key_mailbox) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant |
| [**start_conversation**](AgentsApi.md#start_conversation) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream) |
| [**whoami**](AgentsApi.md#whoami) | **GET** /v1/auth/whoami | Introspect the calling credentials |


## download_thread_attachment

> download_thread_attachment(thread_id, message_id, idx)

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
  api_instance.download_thread_attachment(thread_id, message_id, idx)
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->download_thread_attachment: #{e}"
end
```

#### Using the download_thread_attachment_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> download_thread_attachment_with_http_info(thread_id, message_id, idx)

```ruby
begin
  # Download an attachment
  data, status_code, headers = api_instance.download_thread_attachment_with_http_info(thread_id, message_id, idx)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->download_thread_attachment_with_http_info: #{e}"
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


## get_thread

> <Thread> get_thread(thread_id)

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
  result = api_instance.get_thread(thread_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->get_thread: #{e}"
end
```

#### Using the get_thread_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Thread>, Integer, Hash)> get_thread_with_http_info(thread_id)

```ruby
begin
  # Get a whole conversation
  data, status_code, headers = api_instance.get_thread_with_http_info(thread_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Thread>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->get_thread_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |

### Return type

[**Thread**](Thread.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_thread_message

> <ThreadMessageBody> get_thread_message(thread_id, message_id)

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
  result = api_instance.get_thread_message(thread_id, message_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->get_thread_message: #{e}"
end
```

#### Using the get_thread_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ThreadMessageBody>, Integer, Hash)> get_thread_message_with_http_info(thread_id, message_id)

```ruby
begin
  # Get one message with body
  data, status_code, headers = api_instance.get_thread_message_with_http_info(thread_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ThreadMessageBody>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->get_thread_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

[**ThreadMessageBody**](ThreadMessageBody.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## grant_api_key_mailbox

> <MailboxGrant> grant_api_key_mailbox(key_id)

Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key, the server cannot read E2E mailboxes.

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
  result = api_instance.grant_api_key_mailbox(key_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->grant_api_key_mailbox: #{e}"
end
```

#### Using the grant_api_key_mailbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MailboxGrant>, Integer, Hash)> grant_api_key_mailbox_with_http_info(key_id)

```ruby
begin
  # Grant a mailbox to a key
  data, status_code, headers = api_instance.grant_api_key_mailbox_with_http_info(key_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MailboxGrant>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->grant_api_key_mailbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key_id** | **String** |  |  |

### Return type

[**MailboxGrant**](MailboxGrant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_api_key_mailboxes

> <MailboxGrantList> list_api_key_mailboxes(key_id)

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
  result = api_instance.list_api_key_mailboxes(key_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_api_key_mailboxes: #{e}"
end
```

#### Using the list_api_key_mailboxes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MailboxGrantList>, Integer, Hash)> list_api_key_mailboxes_with_http_info(key_id)

```ruby
begin
  # List a key's mailbox grants
  data, status_code, headers = api_instance.list_api_key_mailboxes_with_http_info(key_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MailboxGrantList>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_api_key_mailboxes_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key_id** | **String** |  |  |

### Return type

[**MailboxGrantList**](MailboxGrantList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_inboxes

> <InboxList> list_inboxes

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
  result = api_instance.list_inboxes
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_inboxes: #{e}"
end
```

#### Using the list_inboxes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InboxList>, Integer, Hash)> list_inboxes_with_http_info

```ruby
begin
  # List granted inboxes
  data, status_code, headers = api_instance.list_inboxes_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InboxList>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_inboxes_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**InboxList**](InboxList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_threads

> <ThreadList> list_threads(mailbox, opts)

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
  result = api_instance.list_threads(mailbox, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_threads: #{e}"
end
```

#### Using the list_threads_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ThreadList>, Integer, Hash)> list_threads_with_http_info(mailbox, opts)

```ruby
begin
  # List conversation threads
  data, status_code, headers = api_instance.list_threads_with_http_info(mailbox, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ThreadList>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->list_threads_with_http_info: #{e}"
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

[**ThreadList**](ThreadList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## lookup_contact

> <ContactLookup> lookup_contact(email)

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
  result = api_instance.lookup_contact(email)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->lookup_contact: #{e}"
end
```

#### Using the lookup_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactLookup>, Integer, Hash)> lookup_contact_with_http_info(email)

```ruby
begin
  # Who is this sender?
  data, status_code, headers = api_instance.lookup_contact_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactLookup>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->lookup_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

[**ContactLookup**](ContactLookup.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_thread_message_read

> <MarkReadResult> mark_thread_message_read(thread_id, message_id)

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
  result = api_instance.mark_thread_message_read(thread_id, message_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->mark_thread_message_read: #{e}"
end
```

#### Using the mark_thread_message_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MarkReadResult>, Integer, Hash)> mark_thread_message_read_with_http_info(thread_id, message_id)

```ruby
begin
  # Mark read/unread
  data, status_code, headers = api_instance.mark_thread_message_read_with_http_info(thread_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MarkReadResult>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->mark_thread_message_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

[**MarkReadResult**](MarkReadResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## reply_to_thread

> <AgentSendResult> reply_to_thread(thread_id, idempotency_key)

Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation, a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.

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
  result = api_instance.reply_to_thread(thread_id, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->reply_to_thread: #{e}"
end
```

#### Using the reply_to_thread_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentSendResult>, Integer, Hash)> reply_to_thread_with_http_info(thread_id, idempotency_key)

```ruby
begin
  # Reply in-thread (agent stream)
  data, status_code, headers = api_instance.reply_to_thread_with_http_info(thread_id, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentSendResult>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->reply_to_thread_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **idempotency_key** | **String** |  |  |

### Return type

[**AgentSendResult**](AgentSendResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_api_key_mailbox

> revoke_api_key_mailbox(key_id, mailbox_id)

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
  api_instance.revoke_api_key_mailbox(key_id, mailbox_id)
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->revoke_api_key_mailbox: #{e}"
end
```

#### Using the revoke_api_key_mailbox_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_api_key_mailbox_with_http_info(key_id, mailbox_id)

```ruby
begin
  # Revoke a mailbox grant
  data, status_code, headers = api_instance.revoke_api_key_mailbox_with_http_info(key_id, mailbox_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->revoke_api_key_mailbox_with_http_info: #{e}"
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


## start_conversation

> <AgentSendResult> start_conversation(mailbox, idempotency_key, start_conversation_request)

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
start_conversation_request = Lockally::StartConversationRequest.new({to: ['to_example'], text: 'text_example'}) # StartConversationRequest | 

begin
  # Start a new conversation (agent stream)
  result = api_instance.start_conversation(mailbox, idempotency_key, start_conversation_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->start_conversation: #{e}"
end
```

#### Using the start_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentSendResult>, Integer, Hash)> start_conversation_with_http_info(mailbox, idempotency_key, start_conversation_request)

```ruby
begin
  # Start a new conversation (agent stream)
  data, status_code, headers = api_instance.start_conversation_with_http_info(mailbox, idempotency_key, start_conversation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentSendResult>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->start_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox** | **String** |  |  |
| **idempotency_key** | **String** |  |  |
| **start_conversation_request** | [**StartConversationRequest**](StartConversationRequest.md) |  |  |

### Return type

[**AgentSendResult**](AgentSendResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## whoami

> <Whoami> whoami

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
  result = api_instance.whoami
  p result
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->whoami: #{e}"
end
```

#### Using the whoami_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Whoami>, Integer, Hash)> whoami_with_http_info

```ruby
begin
  # Introspect the calling credentials
  data, status_code, headers = api_instance.whoami_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Whoami>
rescue Lockally::ApiError => e
  puts "Error when calling AgentsApi->whoami_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Whoami**](Whoami.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

