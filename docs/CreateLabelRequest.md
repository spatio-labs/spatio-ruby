# Spatio::CreateLabelRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **message_list_visibility** | **String** |  | [optional] |
| **label_list_visibility** | **String** |  | [optional] |
| **color** | [**LabelColor**](LabelColor.md) |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateLabelRequest.new(
  account_id: null,
  name: null,
  message_list_visibility: null,
  label_list_visibility: null,
  color: null
)
```

