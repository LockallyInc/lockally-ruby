# Lockally::Contact

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **name** | **String** |  |  |
| **email** | **String** |  |  |
| **phone** | **String** |  | [optional] |
| **company** | **String** |  | [optional] |
| **notes** | **String** |  | [optional] |
| **contact_type** | **String** |  |  |
| **source** | **String** |  | [optional] |
| **department** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Contact.new(
  id: null,
  tenant_id: null,
  name: null,
  email: null,
  phone: null,
  company: null,
  notes: null,
  contact_type: null,
  source: null,
  department: null,
  role: null,
  status: null,
  created_at: null,
  updated_at: null
)
```

