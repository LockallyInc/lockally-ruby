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
| **external_system** | **String** | The system that owns this contact&#39;s external id. Absent on contacts made by hand. | [optional] |
| **external_id** | **String** | The contact&#39;s id in &#x60;external_system&#x60;. Absent on contacts made by hand. | [optional] |

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
  updated_at: null,
  external_system: null,
  external_id: null
)
```

