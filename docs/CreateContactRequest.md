# Lockally::CreateContactRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **email** | **String** |  |  |
| **phone** | **String** |  | [optional] |
| **company** | **String** |  | [optional] |
| **notes** | **String** |  | [optional] |
| **contact_type** | **String** |  | [optional][default to &#39;external&#39;] |
| **department** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateContactRequest.new(
  name: null,
  email: null,
  phone: null,
  company: null,
  notes: null,
  contact_type: null,
  department: null,
  role: null
)
```

