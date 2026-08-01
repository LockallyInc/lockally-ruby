# Lockally::ContactListsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_contact_list_member**](ContactListsApi.md#add_contact_list_member) | **POST** /v1/contact-lists/{id}/members | Add a member to a contact list |
| [**create_contact_list**](ContactListsApi.md#create_contact_list) | **POST** /v1/contact-lists | Create a contact list |
| [**delete_contact_list**](ContactListsApi.md#delete_contact_list) | **DELETE** /v1/contact-lists/{id} | Delete a contact list |
| [**get_contact_list**](ContactListsApi.md#get_contact_list) | **GET** /v1/contact-lists/{id} | Get a contact list with members |
| [**list_contact_lists**](ContactListsApi.md#list_contact_lists) | **GET** /v1/contact-lists | List contact lists |
| [**remove_contact_list_member**](ContactListsApi.md#remove_contact_list_member) | **DELETE** /v1/contact-lists/{id}/members/{contactId} | Remove a member from a contact list |
| [**update_contact_list**](ContactListsApi.md#update_contact_list) | **PATCH** /v1/contact-lists/{id} | Update a contact list |


## add_contact_list_member

> add_contact_list_member(id, add_contact_list_member_request)

Add a member to a contact list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
add_contact_list_member_request = Lockally::AddContactListMemberRequest.new({contact_id: 'contact_id_example'}) # AddContactListMemberRequest | 

begin
  # Add a member to a contact list
  api_instance.add_contact_list_member(id, add_contact_list_member_request)
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->add_contact_list_member: #{e}"
end
```

#### Using the add_contact_list_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> add_contact_list_member_with_http_info(id, add_contact_list_member_request)

```ruby
begin
  # Add a member to a contact list
  data, status_code, headers = api_instance.add_contact_list_member_with_http_info(id, add_contact_list_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->add_contact_list_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **add_contact_list_member_request** | [**AddContactListMemberRequest**](AddContactListMemberRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/problem+json


## create_contact_list

> <ContactList> create_contact_list(create_contact_list_request)

Create a contact list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
create_contact_list_request = Lockally::CreateContactListRequest.new({name: 'name_example'}) # CreateContactListRequest | 

begin
  # Create a contact list
  result = api_instance.create_contact_list(create_contact_list_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->create_contact_list: #{e}"
end
```

#### Using the create_contact_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactList>, Integer, Hash)> create_contact_list_with_http_info(create_contact_list_request)

```ruby
begin
  # Create a contact list
  data, status_code, headers = api_instance.create_contact_list_with_http_info(create_contact_list_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactList>
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->create_contact_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_contact_list_request** | [**CreateContactListRequest**](CreateContactListRequest.md) |  |  |

### Return type

[**ContactList**](ContactList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json


## delete_contact_list

> delete_contact_list(id)

Delete a contact list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Delete a contact list
  api_instance.delete_contact_list(id)
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->delete_contact_list: #{e}"
end
```

#### Using the delete_contact_list_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_contact_list_with_http_info(id)

```ruby
begin
  # Delete a contact list
  data, status_code, headers = api_instance.delete_contact_list_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->delete_contact_list_with_http_info: #{e}"
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


## get_contact_list

> <GetContactList200Response> get_contact_list(id)

Get a contact list with members

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a contact list with members
  result = api_instance.get_contact_list(id)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->get_contact_list: #{e}"
end
```

#### Using the get_contact_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetContactList200Response>, Integer, Hash)> get_contact_list_with_http_info(id)

```ruby
begin
  # Get a contact list with members
  data, status_code, headers = api_instance.get_contact_list_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetContactList200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->get_contact_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**GetContactList200Response**](GetContactList200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## list_contact_lists

> <ListContactLists200Response> list_contact_lists

List contact lists

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new

begin
  # List contact lists
  result = api_instance.list_contact_lists
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->list_contact_lists: #{e}"
end
```

#### Using the list_contact_lists_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListContactLists200Response>, Integer, Hash)> list_contact_lists_with_http_info

```ruby
begin
  # List contact lists
  data, status_code, headers = api_instance.list_contact_lists_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListContactLists200Response>
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->list_contact_lists_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListContactLists200Response**](ListContactLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, application/problem+json


## remove_contact_list_member

> remove_contact_list_member(id, contact_id)

Remove a member from a contact list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
contact_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Remove a member from a contact list
  api_instance.remove_contact_list_member(id, contact_id)
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->remove_contact_list_member: #{e}"
end
```

#### Using the remove_contact_list_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_contact_list_member_with_http_info(id, contact_id)

```ruby
begin
  # Remove a member from a contact list
  data, status_code, headers = api_instance.remove_contact_list_member_with_http_info(id, contact_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->remove_contact_list_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **contact_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/problem+json


## update_contact_list

> <ContactList> update_contact_list(id, update_contact_list_request)

Update a contact list

### Examples

```ruby
require 'time'
require 'lockally'
# setup authorization
Lockally.configure do |config|
  # Configure Bearer authorization (lk_live_<prefix>_<secret>): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Lockally::ContactListsApi.new
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 
update_contact_list_request = Lockally::UpdateContactListRequest.new # UpdateContactListRequest | 

begin
  # Update a contact list
  result = api_instance.update_contact_list(id, update_contact_list_request)
  p result
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->update_contact_list: #{e}"
end
```

#### Using the update_contact_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactList>, Integer, Hash)> update_contact_list_with_http_info(id, update_contact_list_request)

```ruby
begin
  # Update a contact list
  data, status_code, headers = api_instance.update_contact_list_with_http_info(id, update_contact_list_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactList>
rescue Lockally::ApiError => e
  puts "Error when calling ContactListsApi->update_contact_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_contact_list_request** | [**UpdateContactListRequest**](UpdateContactListRequest.md) |  |  |

### Return type

[**ContactList**](ContactList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json, application/problem+json

