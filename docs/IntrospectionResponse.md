# Spatio::IntrospectionResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **active** | **Boolean** |  |  |
| **token_type** | **String** | &#x60;oauth&#x60; or &#x60;pat&#x60;. | [optional] |
| **client_id** | **String** |  | [optional] |
| **user_id** | **String** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **scope** | **String** |  | [optional] |
| **exp** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::IntrospectionResponse.new(
  active: null,
  token_type: null,
  client_id: null,
  user_id: null,
  workspace_id: null,
  scope: null,
  exp: null
)
```

