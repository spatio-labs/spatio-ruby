# Spatio::UpdateBlockRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content** | [**BlockContent**](BlockContent.md) |  | [optional] |
| **properties** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **archived** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateBlockRequest.new(
  content: null,
  properties: null,
  archived: null
)
```

