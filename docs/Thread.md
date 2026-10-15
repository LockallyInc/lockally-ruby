# Lockally::Thread

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread** | [**ThreadSummary**](ThreadSummary.md) |  |  |
| **mailbox** | **String** |  |  |
| **messages** | [**Array&lt;ThreadMessage&gt;**](ThreadMessage.md) | Chronological. Reading never marks a message read. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::Thread.new(
  thread: null,
  mailbox: null,
  messages: null
)
```

