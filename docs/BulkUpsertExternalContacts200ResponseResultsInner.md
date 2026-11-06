# Lockally::BulkUpsertExternalContacts200ResponseResultsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **index** | **Integer** |  |  |
| **external_id** | **String** |  |  |
| **status** | **String** |  |  |
| **contact** | [**Contact**](Contact.md) |  | [optional] |
| **error** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::BulkUpsertExternalContacts200ResponseResultsInner.new(
  index: null,
  external_id: null,
  status: null,
  contact: null,
  error: null
)
```

