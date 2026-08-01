# Lockally::GetAuditSummary200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **admin_actions_today** | **Integer** |  | [optional] |
| **recent_logins** | [**Array&lt;AuditEvent&gt;**](AuditEvent.md) |  | [optional] |
| **recent_exports** | [**Array&lt;AuditEvent&gt;**](AuditEvent.md) |  | [optional] |
| **deleted_mailboxes** | [**Array&lt;AuditEvent&gt;**](AuditEvent.md) |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'lockally'

instance = Lockally::GetAuditSummary200Response.new(
  admin_actions_today: null,
  recent_logins: null,
  recent_exports: null,
  deleted_mailboxes: null,
  generated_at: null
)
```

