# Lockally::Annotations

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **attachment_types** | **Array&lt;String&gt;** |  | [optional] |
| **meeting_request** | **Boolean** |  | [optional] |
| **injection_risk** | [**InjectionRisk**](InjectionRisk.md) |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Annotations.new(
  attachment_types: null,
  meeting_request: null,
  injection_risk: null
)
```

