# Lockally::CreateApiKey201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **tenant_id** | **String** |  |  |
| **prefix** | **String** | 8-char public prefix; safe to store and display. |  |
| **scopes** | **Array&lt;String&gt;** |  |  |
| **label** | **String** |  |  |
| **last_used_at** | **Time** |  | [optional] |
| **revoked_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **test** | **Boolean** | True for an lk_test_* key: the whole request path runs but a send never reaches the mail server and nothing counts against the account. | [optional] |
| **expires_at** | **Time** | When the key stops authenticating. Null means it does not expire, which is how every key behaved before expiry existed. Enforced at authentication, so the key fails the first request after this moment rather than whenever a sweep runs.  | [optional] |
| **rotated_to** | **String** | The successor issued by &#x60;POST /v1/api-keys/{id}/rotate&#x60;. Set on the PREDECESSOR, so you can see which key replaced this one while both still work through the overlap window.  | [optional] |
| **secret** | **String** | The full &#x60;lk_live_&lt;prefix&gt;_&lt;secret&gt;&#x60; token. Shown ONCE. |  |

## Example

```ruby
require 'lockally'

instance = Lockally::CreateApiKey201Response.new(
  id: null,
  tenant_id: null,
  prefix: fbl73bhj,
  scopes: null,
  label: ci-pipeline,
  last_used_at: null,
  revoked_at: null,
  created_at: null,
  test: null,
  expires_at: null,
  rotated_to: null,
  secret: lk_live_fbl73bhj_sfvqy7y757cnvu33bgqdpyrrhq3tyyf3
)
```

