# Lockally::GetEncryptionKey200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **public_key** | **String** |  | [optional] |
| **encrypted_private_key** | **String** |  | [optional] |
| **kdf_params** | **Object** |  | [optional] |
| **version** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetEncryptionKey200Response.new(
  id: null,
  email: null,
  public_key: null,
  encrypted_private_key: null,
  kdf_params: null,
  version: null
)
```

