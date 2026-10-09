# Lockally::DraftsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_drafts_draft_id_approve_post**](DraftsApi.md#v1_drafts_draft_id_approve_post) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human) |
| [**v1_drafts_draft_id_cancel_post**](DraftsApi.md#v1_drafts_draft_id_cancel_post) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft |
| [**v1_drafts_draft_id_get**](DraftsApi.md#v1_drafts_draft_id_get) | **GET** /v1/drafts/{draftID} | Get a draft |
| [**v1_drafts_draft_id_reject_post**](DraftsApi.md#v1_drafts_draft_id_reject_post) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human) |
| [**v1_drafts_get**](DraftsApi.md#v1_drafts_get) | **GET** /v1/drafts | List drafts |
| [**v1_inboxes_mailbox_drafts_post**](DraftsApi.md#v1_inboxes_mailbox_drafts_post) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft |
| [**v1_threads_thread_id_drafts_post**](DraftsApi.md#v1_threads_thread_id_drafts_post) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft |


## v1_drafts_draft_id_approve_post

> Object v1_drafts_draft_id_approve_post(draft_id)

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
  result = api_instance.v1_drafts_draft_id_approve_post(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_approve_post: #{e}"
end
```

#### Using the v1_drafts_draft_id_approve_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_drafts_draft_id_approve_post_with_http_info(draft_id)

```ruby
begin
  # Approve a pending draft (human)
  data, status_code, headers = api_instance.v1_drafts_draft_id_approve_post_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_approve_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_drafts_draft_id_cancel_post

> Object v1_drafts_draft_id_cancel_post(draft_id)

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
  result = api_instance.v1_drafts_draft_id_cancel_post(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_cancel_post: #{e}"
end
```

#### Using the v1_drafts_draft_id_cancel_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_drafts_draft_id_cancel_post_with_http_info(draft_id)

```ruby
begin
  # Withdraw a pending draft
  data, status_code, headers = api_instance.v1_drafts_draft_id_cancel_post_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_cancel_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_drafts_draft_id_get

> Object v1_drafts_draft_id_get(draft_id)

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
  result = api_instance.v1_drafts_draft_id_get(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_get: #{e}"
end
```

#### Using the v1_drafts_draft_id_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_drafts_draft_id_get_with_http_info(draft_id)

```ruby
begin
  # Get a draft
  data, status_code, headers = api_instance.v1_drafts_draft_id_get_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_drafts_draft_id_reject_post

> Object v1_drafts_draft_id_reject_post(draft_id)

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
  result = api_instance.v1_drafts_draft_id_reject_post(draft_id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_reject_post: #{e}"
end
```

#### Using the v1_drafts_draft_id_reject_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_drafts_draft_id_reject_post_with_http_info(draft_id)

```ruby
begin
  # Reject a pending draft (human)
  data, status_code, headers = api_instance.v1_drafts_draft_id_reject_post_with_http_info(draft_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_draft_id_reject_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_drafts_get

> Object v1_drafts_get(opts)

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
  result = api_instance.v1_drafts_get(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_get: #{e}"
end
```

#### Using the v1_drafts_get_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_drafts_get_with_http_info(opts)

```ruby
begin
  # List drafts
  data, status_code, headers = api_instance.v1_drafts_get_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_drafts_get_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_inboxes_mailbox_drafts_post

> Object v1_inboxes_mailbox_drafts_post(mailbox, idempotency_key)

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
  result = api_instance.v1_inboxes_mailbox_drafts_post(mailbox, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_inboxes_mailbox_drafts_post: #{e}"
end
```

#### Using the v1_inboxes_mailbox_drafts_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_inboxes_mailbox_drafts_post_with_http_info(mailbox, idempotency_key)

```ruby
begin
  # Propose a new conversation as a draft
  data, status_code, headers = api_instance.v1_inboxes_mailbox_drafts_post_with_http_info(mailbox, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_inboxes_mailbox_drafts_post_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox** | **String** |  |  |
| **idempotency_key** | **String** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## v1_threads_thread_id_drafts_post

> Object v1_threads_thread_id_drafts_post(thread_id, idempotency_key)

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
  result = api_instance.v1_threads_thread_id_drafts_post(thread_id, idempotency_key)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_threads_thread_id_drafts_post: #{e}"
end
```

#### Using the v1_threads_thread_id_drafts_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_threads_thread_id_drafts_post_with_http_info(thread_id, idempotency_key)

```ruby
begin
  # Propose a reply as a draft
  data, status_code, headers = api_instance.v1_threads_thread_id_drafts_post_with_http_info(thread_id, idempotency_key)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling DraftsApi->v1_threads_thread_id_drafts_post_with_http_info: #{e}"
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

