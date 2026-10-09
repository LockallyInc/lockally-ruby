# Lockally::TestApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**v1_test_inbound_post**](TestApi.md#v1_test_inbound_post) | **POST** /v1/test/inbound | Simulate an inbound email (test keys only) |


## v1_test_inbound_post

> Object v1_test_inbound_post

Simulate an inbound email (test keys only)

Runs a synthetic message through the REAL indexing pipeline — thread adoption, deterministic extraction (incl. injection_risk), and the message.received webhook — so the whole agent loop is testable without a real domain or MTA. Requires an lk_test_* key (create with {\"test\": true} on POST /v1/api-keys). Body: {mailbox, from, subject, text, in_reply_to?, references?}.

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::TestApi.new

begin
  # Simulate an inbound email (test keys only)
  result = api_instance.v1_test_inbound_post
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TestApi->v1_test_inbound_post: #{e}"
end
```

#### Using the v1_test_inbound_post_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Object, Integer, Hash)> v1_test_inbound_post_with_http_info

```ruby
begin
  # Simulate an inbound email (test keys only)
  data, status_code, headers = api_instance.v1_test_inbound_post_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Object
rescue Lockally::ApiError => e
  puts "Error when calling TestApi->v1_test_inbound_post_with_http_info: #{e}"
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

