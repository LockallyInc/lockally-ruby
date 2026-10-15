# Lockally::Classification

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **intent** | **String** | For example support_request, sales_lead, billing, spam. | [optional] |
| **urgency** | **String** |  | [optional] |
| **summary** | **String** | One line. | [optional] |
| **suggested_action** | **String** | One line. | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Classification.new(
  intent: null,
  urgency: null,
  summary: null,
  suggested_action: null
)
```

