# Spatio::CreatePATRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **scopes** | **Array&lt;String&gt;** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreatePATRequest.new(
  name: null,
  description: null,
  scopes: null,
  workspace_id: null,
  expires_at: null
)
```

