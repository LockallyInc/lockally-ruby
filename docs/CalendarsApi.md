# Lockally::CalendarsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_calendar_member**](CalendarsApi.md#add_calendar_member) | **POST** /v1/calendars/{id}/members | Add a member to a calendar |
| [**create_calendar**](CalendarsApi.md#create_calendar) | **POST** /v1/calendars | Create a calendar |
| [**create_calendar_event**](CalendarsApi.md#create_calendar_event) | **POST** /v1/calendars/{id}/events | Create an event in a calendar |
| [**create_calendar_integration**](CalendarsApi.md#create_calendar_integration) | **POST** /v1/calendar-integrations | Create a calendar integration |
| [**delete_calendar**](CalendarsApi.md#delete_calendar) | **DELETE** /v1/calendars/{id} | Delete a calendar |
| [**delete_calendar_event**](CalendarsApi.md#delete_calendar_event) | **DELETE** /v1/calendars/{id}/events/{eventId} | Delete a calendar event |
| [**delete_calendar_integration**](CalendarsApi.md#delete_calendar_integration) | **DELETE** /v1/calendar-integrations/{id} | Delete a calendar integration |
| [**get_calendar**](CalendarsApi.md#get_calendar) | **GET** /v1/calendars/{id} | Get a calendar |
| [**get_calendar_policies**](CalendarsApi.md#get_calendar_policies) | **GET** /v1/calendar-policies | Get calendar policies |
| [**get_calendar_security**](CalendarsApi.md#get_calendar_security) | **GET** /v1/calendar-security | Get calendar security overview |
| [**list_calendar_events**](CalendarsApi.md#list_calendar_events) | **GET** /v1/calendars/{id}/events | List events in a calendar |
| [**list_calendar_integrations**](CalendarsApi.md#list_calendar_integrations) | **GET** /v1/calendar-integrations | List calendar integrations |
| [**list_calendar_members**](CalendarsApi.md#list_calendar_members) | **GET** /v1/calendars/{id}/members | List calendar members |
| [**list_calendars**](CalendarsApi.md#list_calendars) | **GET** /v1/calendars | List calendars |
| [**remove_calendar_member**](CalendarsApi.md#remove_calendar_member) | **DELETE** /v1/calendars/{id}/members/{memberId} | Remove a member from a calendar |
| [**sync_calendar_integration**](CalendarsApi.md#sync_calendar_integration) | **POST** /v1/calendar-integrations/{id}/sync | Trigger sync for a calendar integration |
| [**update_calendar**](CalendarsApi.md#update_calendar) | **PATCH** /v1/calendars/{id} | Update a calendar |
| [**update_calendar_event**](CalendarsApi.md#update_calendar_event) | **PATCH** /v1/calendars/{id}/events/{eventId} | Update a calendar event |
| [**update_calendar_integration**](CalendarsApi.md#update_calendar_integration) | **PATCH** /v1/calendar-integrations/{id} | Update a calendar integration |
| [**update_calendar_member**](CalendarsApi.md#update_calendar_member) | **PATCH** /v1/calendars/{id}/members/{memberId} | Update a calendar member&#39;s role |
| [**update_calendar_policies**](CalendarsApi.md#update_calendar_policies) | **PATCH** /v1/calendar-policies | Update calendar policies |


## add_calendar_member

> <CalendarMember> add_calendar_member(id, add_calendar_member_request)

Add a member to a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
add_calendar_member_request = Lockally::AddCalendarMemberRequest.new({user_email: 'user_email_example'}) # AddCalendarMemberRequest | 

begin
  # Add a member to a calendar
  result = api_instance.add_calendar_member(id, add_calendar_member_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->add_calendar_member: #{e}"
end
```

#### Using the add_calendar_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarMember>, Integer, Hash)> add_calendar_member_with_http_info(id, add_calendar_member_request)

```ruby
begin
  # Add a member to a calendar
  data, status_code, headers = api_instance.add_calendar_member_with_http_info(id, add_calendar_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarMember>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->add_calendar_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **add_calendar_member_request** | [**AddCalendarMemberRequest**](AddCalendarMemberRequest.md) |  |  |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_calendar

> <Calendar> create_calendar(create_calendar_request)

Create a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
create_calendar_request = Lockally::CreateCalendarRequest.new({name: 'name_example'}) # CreateCalendarRequest | 

begin
  # Create a calendar
  result = api_instance.create_calendar(create_calendar_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar: #{e}"
end
```

#### Using the create_calendar_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Calendar>, Integer, Hash)> create_calendar_with_http_info(create_calendar_request)

```ruby
begin
  # Create a calendar
  data, status_code, headers = api_instance.create_calendar_with_http_info(create_calendar_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Calendar>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_calendar_request** | [**CreateCalendarRequest**](CreateCalendarRequest.md) |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_calendar_event

> <CalendarEvent> create_calendar_event(id, create_calendar_event_request)

Create an event in a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
create_calendar_event_request = Lockally::CreateCalendarEventRequest.new({title: 'title_example', starts_at: Time.now, ends_at: Time.now}) # CreateCalendarEventRequest | 

begin
  # Create an event in a calendar
  result = api_instance.create_calendar_event(id, create_calendar_event_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar_event: #{e}"
end
```

#### Using the create_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarEvent>, Integer, Hash)> create_calendar_event_with_http_info(id, create_calendar_event_request)

```ruby
begin
  # Create an event in a calendar
  data, status_code, headers = api_instance.create_calendar_event_with_http_info(id, create_calendar_event_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarEvent>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **create_calendar_event_request** | [**CreateCalendarEventRequest**](CreateCalendarEventRequest.md) |  |  |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## create_calendar_integration

> <CalendarIntegration> create_calendar_integration(create_calendar_integration_request)

Create a calendar integration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
create_calendar_integration_request = Lockally::CreateCalendarIntegrationRequest.new({provider: 'exchange'}) # CreateCalendarIntegrationRequest | 

begin
  # Create a calendar integration
  result = api_instance.create_calendar_integration(create_calendar_integration_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar_integration: #{e}"
end
```

#### Using the create_calendar_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarIntegration>, Integer, Hash)> create_calendar_integration_with_http_info(create_calendar_integration_request)

```ruby
begin
  # Create a calendar integration
  data, status_code, headers = api_instance.create_calendar_integration_with_http_info(create_calendar_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarIntegration>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->create_calendar_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_calendar_integration_request** | [**CreateCalendarIntegrationRequest**](CreateCalendarIntegrationRequest.md) |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_calendar

> delete_calendar(id)

Delete a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a calendar
  api_instance.delete_calendar(id)
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar: #{e}"
end
```

#### Using the delete_calendar_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_calendar_with_http_info(id)

```ruby
begin
  # Delete a calendar
  data, status_code, headers = api_instance.delete_calendar_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## delete_calendar_event

> delete_calendar_event(id, event_id)

Delete a calendar event

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
event_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a calendar event
  api_instance.delete_calendar_event(id, event_id)
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar_event: #{e}"
end
```

#### Using the delete_calendar_event_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_calendar_event_with_http_info(id, event_id)

```ruby
begin
  # Delete a calendar event
  data, status_code, headers = api_instance.delete_calendar_event_with_http_info(id, event_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **event_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## delete_calendar_integration

> delete_calendar_integration(id)

Delete a calendar integration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a calendar integration
  api_instance.delete_calendar_integration(id)
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar_integration: #{e}"
end
```

#### Using the delete_calendar_integration_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_calendar_integration_with_http_info(id)

```ruby
begin
  # Delete a calendar integration
  data, status_code, headers = api_instance.delete_calendar_integration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->delete_calendar_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## get_calendar

> <Calendar> get_calendar(id)

Get a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a calendar
  result = api_instance.get_calendar(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar: #{e}"
end
```

#### Using the get_calendar_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Calendar>, Integer, Hash)> get_calendar_with_http_info(id)

```ruby
begin
  # Get a calendar
  data, status_code, headers = api_instance.get_calendar_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Calendar>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_calendar_policies

> <CalendarPolicies> get_calendar_policies

Get calendar policies

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new

begin
  # Get calendar policies
  result = api_instance.get_calendar_policies
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar_policies: #{e}"
end
```

#### Using the get_calendar_policies_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarPolicies>, Integer, Hash)> get_calendar_policies_with_http_info

```ruby
begin
  # Get calendar policies
  data, status_code, headers = api_instance.get_calendar_policies_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarPolicies>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar_policies_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_calendar_security

> <GetCalendarSecurity200Response> get_calendar_security

Get calendar security overview

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new

begin
  # Get calendar security overview
  result = api_instance.get_calendar_security
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar_security: #{e}"
end
```

#### Using the get_calendar_security_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetCalendarSecurity200Response>, Integer, Hash)> get_calendar_security_with_http_info

```ruby
begin
  # Get calendar security overview
  data, status_code, headers = api_instance.get_calendar_security_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetCalendarSecurity200Response>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->get_calendar_security_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetCalendarSecurity200Response**](GetCalendarSecurity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_calendar_events

> <ListCalendarEvents200Response> list_calendar_events(id, opts)

List events in a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
opts = {
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # List events in a calendar
  result = api_instance.list_calendar_events(id, opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_events: #{e}"
end
```

#### Using the list_calendar_events_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCalendarEvents200Response>, Integer, Hash)> list_calendar_events_with_http_info(id, opts)

```ruby
begin
  # List events in a calendar
  data, status_code, headers = api_instance.list_calendar_events_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCalendarEvents200Response>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_events_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |

### Return type

[**ListCalendarEvents200Response**](ListCalendarEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_calendar_integrations

> <ListCalendarIntegrations200Response> list_calendar_integrations

List calendar integrations

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new

begin
  # List calendar integrations
  result = api_instance.list_calendar_integrations
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_integrations: #{e}"
end
```

#### Using the list_calendar_integrations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCalendarIntegrations200Response>, Integer, Hash)> list_calendar_integrations_with_http_info

```ruby
begin
  # List calendar integrations
  data, status_code, headers = api_instance.list_calendar_integrations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCalendarIntegrations200Response>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_integrations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListCalendarIntegrations200Response**](ListCalendarIntegrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_calendar_members

> <ListCalendarMembers200Response> list_calendar_members(id)

List calendar members

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # List calendar members
  result = api_instance.list_calendar_members(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_members: #{e}"
end
```

#### Using the list_calendar_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCalendarMembers200Response>, Integer, Hash)> list_calendar_members_with_http_info(id)

```ruby
begin
  # List calendar members
  data, status_code, headers = api_instance.list_calendar_members_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCalendarMembers200Response>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendar_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**ListCalendarMembers200Response**](ListCalendarMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_calendars

> <ListCalendars200Response> list_calendars

List calendars

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new

begin
  # List calendars
  result = api_instance.list_calendars
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendars: #{e}"
end
```

#### Using the list_calendars_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCalendars200Response>, Integer, Hash)> list_calendars_with_http_info

```ruby
begin
  # List calendars
  data, status_code, headers = api_instance.list_calendars_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCalendars200Response>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->list_calendars_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListCalendars200Response**](ListCalendars200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## remove_calendar_member

> remove_calendar_member(id, member_id)

Remove a member from a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
member_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Remove a member from a calendar
  api_instance.remove_calendar_member(id, member_id)
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->remove_calendar_member: #{e}"
end
```

#### Using the remove_calendar_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_calendar_member_with_http_info(id, member_id)

```ruby
begin
  # Remove a member from a calendar
  data, status_code, headers = api_instance.remove_calendar_member_with_http_info(id, member_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->remove_calendar_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **member_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## sync_calendar_integration

> <CalendarIntegration> sync_calendar_integration(id)

Trigger sync for a calendar integration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Trigger sync for a calendar integration
  result = api_instance.sync_calendar_integration(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->sync_calendar_integration: #{e}"
end
```

#### Using the sync_calendar_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarIntegration>, Integer, Hash)> sync_calendar_integration_with_http_info(id)

```ruby
begin
  # Trigger sync for a calendar integration
  data, status_code, headers = api_instance.sync_calendar_integration_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarIntegration>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->sync_calendar_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_calendar

> <Calendar> update_calendar(id, update_calendar_request)

Update a calendar

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_calendar_request = Lockally::UpdateCalendarRequest.new # UpdateCalendarRequest | 

begin
  # Update a calendar
  result = api_instance.update_calendar(id, update_calendar_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar: #{e}"
end
```

#### Using the update_calendar_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Calendar>, Integer, Hash)> update_calendar_with_http_info(id, update_calendar_request)

```ruby
begin
  # Update a calendar
  data, status_code, headers = api_instance.update_calendar_with_http_info(id, update_calendar_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Calendar>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_calendar_request** | [**UpdateCalendarRequest**](UpdateCalendarRequest.md) |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_calendar_event

> <CalendarEvent> update_calendar_event(id, event_id, update_calendar_event_request)

Update a calendar event

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
event_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_calendar_event_request = Lockally::UpdateCalendarEventRequest.new # UpdateCalendarEventRequest | 

begin
  # Update a calendar event
  result = api_instance.update_calendar_event(id, event_id, update_calendar_event_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_event: #{e}"
end
```

#### Using the update_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarEvent>, Integer, Hash)> update_calendar_event_with_http_info(id, event_id, update_calendar_event_request)

```ruby
begin
  # Update a calendar event
  data, status_code, headers = api_instance.update_calendar_event_with_http_info(id, event_id, update_calendar_event_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarEvent>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **event_id** | **String** |  |  |
| **update_calendar_event_request** | [**UpdateCalendarEventRequest**](UpdateCalendarEventRequest.md) |  |  |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_calendar_integration

> <CalendarIntegration> update_calendar_integration(id, update_calendar_integration_request)

Update a calendar integration

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_calendar_integration_request = Lockally::UpdateCalendarIntegrationRequest.new # UpdateCalendarIntegrationRequest | 

begin
  # Update a calendar integration
  result = api_instance.update_calendar_integration(id, update_calendar_integration_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_integration: #{e}"
end
```

#### Using the update_calendar_integration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarIntegration>, Integer, Hash)> update_calendar_integration_with_http_info(id, update_calendar_integration_request)

```ruby
begin
  # Update a calendar integration
  data, status_code, headers = api_instance.update_calendar_integration_with_http_info(id, update_calendar_integration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarIntegration>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_integration_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_calendar_integration_request** | [**UpdateCalendarIntegrationRequest**](UpdateCalendarIntegrationRequest.md) |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_calendar_member

> <CalendarMember> update_calendar_member(id, member_id, update_calendar_member_request)

Update a calendar member's role

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
member_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_calendar_member_request = Lockally::UpdateCalendarMemberRequest.new({role: 'viewer'}) # UpdateCalendarMemberRequest | 

begin
  # Update a calendar member's role
  result = api_instance.update_calendar_member(id, member_id, update_calendar_member_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_member: #{e}"
end
```

#### Using the update_calendar_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarMember>, Integer, Hash)> update_calendar_member_with_http_info(id, member_id, update_calendar_member_request)

```ruby
begin
  # Update a calendar member's role
  data, status_code, headers = api_instance.update_calendar_member_with_http_info(id, member_id, update_calendar_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarMember>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **member_id** | **String** |  |  |
| **update_calendar_member_request** | [**UpdateCalendarMemberRequest**](UpdateCalendarMemberRequest.md) |  |  |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## update_calendar_policies

> <CalendarPolicies> update_calendar_policies(update_calendar_policies_request)

Update calendar policies

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::CalendarsApi.new
update_calendar_policies_request = Lockally::UpdateCalendarPoliciesRequest.new # UpdateCalendarPoliciesRequest | 

begin
  # Update calendar policies
  result = api_instance.update_calendar_policies(update_calendar_policies_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_policies: #{e}"
end
```

#### Using the update_calendar_policies_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarPolicies>, Integer, Hash)> update_calendar_policies_with_http_info(update_calendar_policies_request)

```ruby
begin
  # Update calendar policies
  data, status_code, headers = api_instance.update_calendar_policies_with_http_info(update_calendar_policies_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarPolicies>
rescue Lockally::ApiError => e
  puts "Error when calling CalendarsApi->update_calendar_policies_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **update_calendar_policies_request** | [**UpdateCalendarPoliciesRequest**](UpdateCalendarPoliciesRequest.md) |  |  |

### Return type

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

