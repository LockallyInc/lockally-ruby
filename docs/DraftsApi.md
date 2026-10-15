# Lockally::DraftsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**approve_draft**](DraftsApi.md#approve_draft) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human) |
| [**cancel_draft**](DraftsApi.md#cancel_draft) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft |
| [**create_conversation_draft**](DraftsApi.md#create_conversation_draft) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft |
| [**create_reply_draft**](DraftsApi.md#create_reply_draft) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft |
| [**get_draft**](DraftsApi.md#get_draft) | **GET** /v1/drafts/{draftID} | Get a draft |
| [**list_drafts**](DraftsApi.md#list_drafts) | **GET** /v1/drafts | List drafts |
| [**reject_draft**](DraftsApi.md#reject_draft) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human) |


## approve_draft

> <DraftResult> approve_draft(draft_id)

Approve a pending draft (human)

Sends the draft exactly as reviewed, through the agent stream (loop detector included). Fires draft.approved.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
draft_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Approve a pending draft (human)
  result = api_instance.approve_draft(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->approve_draft: #{e}"
end
```

#### Using the approve_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftResult>, Integer, Hash)> approve_draft_with_http_info(draft_id)

```ruby
begin
  # Approve a pending draft (human)
  data, status_code, headers = api_instance.approve_draft_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftResult>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->approve_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## cancel_draft

> <Draft> cancel_draft(draft_id)

Withdraw a pending draft

Only the API key that created the draft may cancel it.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
draft_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Withdraw a pending draft
  result = api_instance.cancel_draft(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->cancel_draft: #{e}"
end
```

#### Using the cancel_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Draft>, Integer, Hash)> cancel_draft_with_http_info(draft_id)

```ruby
begin
  # Withdraw a pending draft
  data, status_code, headers = api_instance.cancel_draft_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Draft>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->cancel_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_conversation_draft

> <DraftResult> create_conversation_draft(mailbox, idempotency_key)

Propose a new conversation as a draft

New-conversation drafts ALWAYS require human approval (policy flag new_thread). Idempotency-Key required.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
mailbox = 'mailbox_example' # String | 
idempotency_key = 'idempotency_key_example' # String | 

begin
  # Propose a new conversation as a draft
  result = api_instance.create_conversation_draft(mailbox, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->create_conversation_draft: #{e}"
end
```

#### Using the create_conversation_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftResult>, Integer, Hash)> create_conversation_draft_with_http_info(mailbox, idempotency_key)

```ruby
begin
  # Propose a new conversation as a draft
  data, status_code, headers = api_instance.create_conversation_draft_with_http_info(mailbox, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftResult>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->create_conversation_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox** | **String** |  |  |
| **idempotency_key** | **String** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_reply_draft

> <DraftResult> create_reply_draft(thread_id, idempotency_key)

Propose a reply as a draft

The safe default over /reply: the deterministic policy engine auto-sends clean in-thread replies and holds anything risky (PII, new recipients, injection-flagged threads, always-approve mailboxes) for human approval. Fires draft.pending_approval when held. Idempotency-Key required.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
thread_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
idempotency_key = 'idempotency_key_example' # String | 

begin
  # Propose a reply as a draft
  result = api_instance.create_reply_draft(thread_id, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->create_reply_draft: #{e}"
end
```

#### Using the create_reply_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftResult>, Integer, Hash)> create_reply_draft_with_http_info(thread_id, idempotency_key)

```ruby
begin
  # Propose a reply as a draft
  data, status_code, headers = api_instance.create_reply_draft_with_http_info(thread_id, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftResult>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->create_reply_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |
| **idempotency_key** | **String** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_draft

> <Draft> get_draft(draft_id)

Get a draft

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
draft_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a draft
  result = api_instance.get_draft(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->get_draft: #{e}"
end
```

#### Using the get_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Draft>, Integer, Hash)> get_draft_with_http_info(draft_id)

```ruby
begin
  # Get a draft
  data, status_code, headers = api_instance.get_draft_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Draft>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->get_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_drafts

> <DraftList> list_drafts(opts)

List drafts

Filter with ?status=pending_approval|sent|rejected|cancelled. Keys see drafts of granted mailboxes; admin sessions see all.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
opts = {
  status: 'status_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List drafts
  result = api_instance.list_drafts(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->list_drafts: #{e}"
end
```

#### Using the list_drafts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftList>, Integer, Hash)> list_drafts_with_http_info(opts)

```ruby
begin
  # List drafts
  data, status_code, headers = api_instance.list_drafts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftList>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->list_drafts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

[**DraftList**](DraftList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## reject_draft

> <Draft> reject_draft(draft_id)

Reject a pending draft (human)

Body: {\"reason\": \"...\"} (optional). Fires draft.rejected.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::DraftsApi.new
draft_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Reject a pending draft (human)
  result = api_instance.reject_draft(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->reject_draft: #{e}"
end
```

#### Using the reject_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Draft>, Integer, Hash)> reject_draft_with_http_info(draft_id)

```ruby
begin
  # Reject a pending draft (human)
  data, status_code, headers = api_instance.reject_draft_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Draft>
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->reject_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

