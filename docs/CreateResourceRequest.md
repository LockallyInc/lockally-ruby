# Lockally::CreateResourceRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **type** | **String** |  | [optional][default to &#39;meeting_room&#39;] |
| **capacity** | **Integer** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateResourceRequest.new(
  name: null,
  type: null,
  capacity: null
)
```

