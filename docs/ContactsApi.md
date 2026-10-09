# Lockally::ContactsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_contact**](ContactsApi.md#create_contact) | **POST** /v1/contacts | Create a contact |
| [**delete_contact**](ContactsApi.md#delete_contact) | **DELETE** /v1/contacts/{id} | Delete a contact |
| [**get_contact**](ContactsApi.md#get_contact) | **GET** /v1/contacts/{id} | Get a contact |
| [**get_contact_lists**](ContactsApi.md#get_contact_lists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to |
| [**list_contacts**](ContactsApi.md#list_contacts) | **GET** /v1/contacts | List contacts |
| [**update_contact**](ContactsApi.md#update_contact) | **PATCH** /v1/contacts/{id} | Update a contact |


## create_contact

> <Contact> create_contact(create_contact_request)

Create a contact

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
create_contact_request = Lockally::CreateContactRequest.new({name: 'name_example', email: 'email_example'}) # CreateContactRequest | 

begin
  # Create a contact
  result = api_instance.create_contact(create_contact_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->create_contact: #{e}"
end
```

#### Using the create_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> create_contact_with_http_info(create_contact_request)

```ruby
begin
  # Create a contact
  data, status_code, headers = api_instance.create_contact_with_http_info(create_contact_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->create_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_contact_request** | [**CreateContactRequest**](CreateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_contact

> delete_contact(id)

Delete a contact

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a contact
  api_instance.delete_contact(id)
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->delete_contact: #{e}"
end
```

#### Using the delete_contact_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_contact_with_http_info(id)

```ruby
begin
  # Delete a contact
  data, status_code, headers = api_instance.delete_contact_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->delete_contact_with_http_info: #{e}"
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


## get_contact

> <Contact> get_contact(id)

Get a contact

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a contact
  result = api_instance.get_contact(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->get_contact: #{e}"
end
```

#### Using the get_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> get_contact_with_http_info(id)

```ruby
begin
  # Get a contact
  data, status_code, headers = api_instance.get_contact_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->get_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## get_contact_lists

> <GetContactLists200Response> get_contact_lists(id)

Get lists a contact belongs to

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get lists a contact belongs to
  result = api_instance.get_contact_lists(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->get_contact_lists: #{e}"
end
```

#### Using the get_contact_lists_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetContactLists200Response>, Integer, Hash)> get_contact_lists_with_http_info(id)

```ruby
begin
  # Get lists a contact belongs to
  data, status_code, headers = api_instance.get_contact_lists_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetContactLists200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->get_contact_lists_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**GetContactLists200Response**](GetContactLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_contacts

> <ListContacts200Response> list_contacts(opts)

List contacts

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
opts = {
  q: 'q_example', # String | Free-text search across name, email, company
  type: 'type_example', # String | Filter by contact_type
  department: 'department_example', # String | Filter by department
  status: 'status_example', # String | Filter by status
  source: 'source_example' # String | Filter by source
}

begin
  # List contacts
  result = api_instance.list_contacts(opts)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->list_contacts: #{e}"
end
```

#### Using the list_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListContacts200Response>, Integer, Hash)> list_contacts_with_http_info(opts)

```ruby
begin
  # List contacts
  data, status_code, headers = api_instance.list_contacts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListContacts200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->list_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **q** | **String** | Free-text search across name, email, company | [optional] |
| **type** | **String** | Filter by contact_type | [optional] |
| **department** | **String** | Filter by department | [optional] |
| **status** | **String** | Filter by status | [optional] |
| **source** | **String** | Filter by source | [optional] |

### Return type

[**ListContacts200Response**](ListContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## update_contact

> <Contact> update_contact(id, update_contact_request)

Update a contact

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_contact_request = Lockally::UpdateContactRequest.new # UpdateContactRequest | 

begin
  # Update a contact
  result = api_instance.update_contact(id, update_contact_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->update_contact: #{e}"
end
```

#### Using the update_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> update_contact_with_http_info(id, update_contact_request)

```ruby
begin
  # Update a contact
  data, status_code, headers = api_instance.update_contact_with_http_info(id, update_contact_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Lockally::ApiError => e
  puts "Error when calling ContactsApi->update_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_contact_request** | [**UpdateContactRequest**](UpdateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

