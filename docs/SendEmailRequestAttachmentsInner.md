# Lockally::SendEmailRequestAttachmentsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **filename** | **String** |  |  |
| **content_type** | **String** |  |  |
| **content_base64** | **String** | Base64-encoded body, max 10 MB decoded per attachment. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::SendEmailRequestAttachmentsInner.new(
  filename: null,
  content_type: application/pdf,
  content_base64: null
)
```

