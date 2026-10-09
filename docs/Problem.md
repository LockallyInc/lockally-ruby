# Lockally::Problem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  | [default to &#39;about:blank&#39;] |
| **status** | **Integer** |  |  |
| **title** | **String** |  |  |
| **detail** | **String** |  | [optional] |
| **instance** | **String** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::Problem.new(
  type: null,
  status: null,
  title: null,
  detail: null,
  instance: null
)
```

