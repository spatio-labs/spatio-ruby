# Spatio::KeyBinding

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **action_id** | **String** |  |  |
| **display_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **key** | **String** |  | [optional] |
| **modifiers** | **Array&lt;String&gt;** |  | [optional] |
| **category** | **String** |  | [optional] |
| **scope** | **String** |  | [optional] |
| **display_order** | **Integer** |  | [optional] |
| **is_custom** | **Boolean** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::KeyBinding.new(
  id: null,
  action_id: null,
  display_name: null,
  description: null,
  key: null,
  modifiers: null,
  category: null,
  scope: null,
  display_order: null,
  is_custom: null,
  metadata: null
)
```

