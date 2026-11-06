# Lockally::SignupRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** | Workspace id. 3 to 63 characters of lowercase a-z, 0-9 and hyphens, starting and ending with a letter or digit. Anything else is refused with 400 Invalid workspace id. |  |
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

