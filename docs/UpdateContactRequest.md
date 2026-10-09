# Lockally::UpdateContactRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **phone** | **String** |  | [optional] |
| **company** | **String** |  | [optional] |
| **notes** | **String** |  | [optional] |
| **contact_type** | **String** |  | [optional] |
| **department** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::UpdateContactRequest.new(
  name: null,
  email: null,
  phone: null,
  company: null,
  notes: null,
  contact_type: null,
  department: null,
  role: null,
  status: null
)
```

