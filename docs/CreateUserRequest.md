# Lockally::CreateUserRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **first_name** | **String** |  |  |
| **last_name** | **String** |  |  |
| **title** | **String** |  | [optional] |
| **department** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateUserRequest.new(
  email: null,
  first_name: null,
  last_name: null,
  title: null,
  department: null
)
```

