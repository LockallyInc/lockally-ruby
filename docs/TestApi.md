# Lockally::TestApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**simulate_inbound_email**](TestApi.md#simulate_inbound_email) | **POST** /v1/test/inbound | Simulate an inbound email (test keys only) |


## simulate_inbound_email

> <SimulatedInbound> simulate_inbound_email

Simulate an inbound email (test keys only)

Runs a synthetic message through the REAL indexing pipeline, thread adoption, deterministic extraction (incl. injection_risk), and the message.received webhook, so the whole agent loop is testable without a real domain or MTA. Requires an lk_test_* key (create with {\"test\": true} on POST /v1/api-keys). Body: {mailbox, from, subject, text, in_reply_to?, references?}.

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
  result = api_instance.simulate_inbound_email
  p result
rescue Lockally::ApiError => e
  puts "Error when calling TestApi->simulate_inbound_email: #{e}"
end
```

#### Using the simulate_inbound_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SimulatedInbound>, Integer, Hash)> simulate_inbound_email_with_http_info

```ruby
begin
  # Simulate an inbound email (test keys only)
  data, status_code, headers = api_instance.simulate_inbound_email_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SimulatedInbound>
rescue Lockally::ApiError => e
  puts "Error when calling TestApi->simulate_inbound_email_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SimulatedInbound**](SimulatedInbound.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

