# Spatio::ChatActionDefinition

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **platform** | **String** |  |  |
| **category** | **String** | Common values: &#x60;read&#x60;, &#x60;write&#x60;, &#x60;delete&#x60;, &#x60;manage&#x60;, &#x60;sync&#x60;. | [optional] |
| **input_type** | **String** |  | [optional] |
| **output_type** | **String** |  | [optional] |
| **scopes** | **Array&lt;String&gt;** | &#x60;null&#x60; when no scopes are declared (Go nil-slice). | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ChatActionDefinition.new(
  id: null,
  name: null,
  description: null,
  platform: null,
  category: null,
  input_type: null,
  output_type: null,
  scopes: null,
  metadata: null
)
```

