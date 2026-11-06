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
| **created_at** | **Time** |  | [optional] |
| **rotated_at** | **Time** |  | [optional] |
| **has_recovery** | **Boolean** |  | [optional] |
| **recovery_set_at** | **Time** |  | [optional] |
| **recovery_blob** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetEncryptionKey200Response.new(
  id: null,
  email: null,
  public_key: null,
  encrypted_private_key: null,
  kdf_params: null,
  version: null,
  created_at: null,
  rotated_at: null,
  has_recovery: null,
  recovery_set_at: null,
  recovery_blob: null
)
```

