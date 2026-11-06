# Lockally::BulkUpsertExternalContactsRequestContactsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **name** | **String** | Defaults to the email address when empty. | [optional] |
| **phone** | **String** |  | [optional] |
| **company** | **String** |  | [optional] |
| **notes** | **String** |  | [optional] |
| **contact_type** | **String** |  | [optional][default to &#39;external&#39;] |
| **department** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |
| **status** | **String** |  | [optional][default to &#39;active&#39;] |
| **external_id** | **String** |  |  |

## Example

```ruby
require 'lockally'

instance = Lockally::BulkUpsertExternalContactsRequestContactsInner.new(
  email: null,
  name: null,
  phone: null,
  company: null,
  notes: null,
  contact_type: null,
  department: null,
  role: null,
  status: null,
  external_id: null
)
```

