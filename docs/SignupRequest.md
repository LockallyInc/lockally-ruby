# Lockally::SignupRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** |  |  |
| **display_name** | **String** |  | [optional] |
| **admin_email** | **String** |  |  |
| **password** | **String** |  |  |
| **mode** | **String** |  | [optional][default to &#39;business&#39;] |

## Example

```ruby
require 'lockally'

instance = Lockally::SignupRequest.new(
  slug: null,
  display_name: null,
  admin_email: null,
  password: null,
  mode: null
)
```

