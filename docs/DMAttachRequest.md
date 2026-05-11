# Spatio::DMAttachRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **kind** | **String** | Attachment kind (&#x60;image&#x60;, &#x60;file&#x60;, &#x60;audio&#x60;, &#x60;video&#x60;, etc.). |  |
| **url** | **String** |  |  |
| **filename** | **String** |  | [optional] |
| **size_bytes** | **Integer** |  | [optional] |
| **mime_type** | **String** |  | [optional] |
| **thumbnail_url** | **String** |  | [optional] |
| **width** | **Integer** |  | [optional] |
| **height** | **Integer** |  | [optional] |
| **account_id** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::DMAttachRequest.new(
  kind: null,
  url: null,
  filename: null,
  size_bytes: null,
  mime_type: null,
  thumbnail_url: null,
  width: null,
  height: null,
  account_id: null
)
```

