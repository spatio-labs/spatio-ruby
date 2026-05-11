# Spatio::AttachmentInput

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **filename** | **String** |  |  |
| **content_type** | **String** |  |  |
| **data** | **String** | Base64-encoded bytes. |  |
| **size** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AttachmentInput.new(
  filename: null,
  content_type: null,
  data: null,
  size: null
)
```

