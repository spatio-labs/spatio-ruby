# Spatio::ConnectedAppItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_id** | **String** |  |  |
| **client_name** | **String** |  |  |
| **logo_uri** | **String** |  | [optional] |
| **client_uri** | **String** |  | [optional] |
| **policy_uri** | **String** |  | [optional] |
| **tos_uri** | **String** |  | [optional] |
| **scopes** | **Array&lt;String&gt;** |  |  |
| **scope_labels** | **Array&lt;String&gt;** |  |  |
| **granted_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ConnectedAppItem.new(
  client_id: null,
  client_name: null,
  logo_uri: null,
  client_uri: null,
  policy_uri: null,
  tos_uri: null,
  scopes: null,
  scope_labels: null,
  granted_at: null
)
```

