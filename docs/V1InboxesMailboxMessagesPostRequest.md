# Lockally::V1InboxesMailboxMessagesPostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **text** | **String** |  |  |
| **html** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::V1InboxesMailboxMessagesPostRequest.new(
  to: null,
  cc: null,
  subject: null,
  text: null,
  html: null
)
```

