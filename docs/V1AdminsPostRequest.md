# Lockally::V1AdminsPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **role** | **String** |  | [optional][default to &#39;admin&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::V1AdminsPostRequest.new(
  email: null,
  password: null,
  display_name: null,
  role: null
)
```

