# Lockally::V1MessagesGet200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **data** | [**Array&lt;Message&gt;**](Message.md) |  |  |
| **next_cursor** | **String** | Pass as &#x60;cursor&#x60; to fetch the next page. Absent on the final page. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::V1MessagesGet200Response.new(
  data: null,
  next_cursor: null
)
```

