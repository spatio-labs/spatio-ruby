# Spatio::Label

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  |  |
| **type** | **String** | Provider-specific label type. Common values: &#x60;system&#x60;, &#x60;user&#x60;. Not enumerated to avoid forcing a breaking change every time a provider adds one.  |  |
| **message_list_visibility** | **String** |  | [optional] |
| **label_list_visibility** | **String** |  | [optional] |
| **color** | [**LabelColor**](LabelColor.md) |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Label.new(
  id: null,
  name: null,
  type: null,
  message_list_visibility: null,
  label_list_visibility: null,
  color: null
)
```

