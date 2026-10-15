# Lockally::Attachment

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **type** | **String** | MIME type. | [optional] |
| **size** | **Integer** | Bytes. | [optional] |
| **blob_id** | **String** |  | [optional] |
| **part_id** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Attachment.new(
  name: null,
  type: null,
  size: null,
  blob_id: null,
  part_id: null
)
```

