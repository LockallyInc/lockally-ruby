# Lockally::RotateEncryptionKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox_email** | **String** |  |  |
| **encrypted_private_key** | **String** |  |  |
| **kdf_params** | **Object** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::RotateEncryptionKeyRequest.new(
  mailbox_email: null,
  encrypted_private_key: null,
  kdf_params: null
)
```

