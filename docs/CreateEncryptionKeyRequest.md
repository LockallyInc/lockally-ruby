# Lockally::CreateEncryptionKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mailbox_email** | **String** |  |  |
| **public_key** | **String** |  |  |
| **encrypted_private_key** | **String** |  |  |
| **kdf_params** | **Object** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateEncryptionKeyRequest.new(
  mailbox_email: null,
  public_key: null,
  encrypted_private_key: null,
  kdf_params: null
)
```

