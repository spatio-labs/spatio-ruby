# Spatio::PersonalAccessToken

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **scopes** | **Array&lt;String&gt;** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **last_used_at** | **Time** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |
| **token_prefix** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::PersonalAccessToken.new(
  id: null,
  name: null,
  description: null,
  scopes: null,
  workspace_id: null,
  created_at: null,
  last_used_at: null,
  expires_at: null,
  token_prefix: null
)
```

