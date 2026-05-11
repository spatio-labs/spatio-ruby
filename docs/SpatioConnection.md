# Spatio::SpatioConnection

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **category** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **auth_type** | **String** |  | [optional] |
| **connected** | **Boolean** |  | [optional] |
| **connected_accounts** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **capabilities** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **gradient_from** | **String** |  | [optional] |
| **gradient_to** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SpatioConnection.new(
  id: null,
  name: null,
  category: null,
  description: null,
  auth_type: null,
  connected: null,
  connected_accounts: null,
  capabilities: null,
  gradient_from: null,
  gradient_to: null,
  icon: null
)
```

