# Spatio::CreateBlockRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | [**BlockType**](BlockType.md) |  |  |
| **content** | [**BlockContent**](BlockContent.md) |  |  |
| **parent_id** | **String** | Parent block id for nested blocks. | [optional] |
| **position** | **Integer** |  |  |
| **properties** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateBlockRequest.new(
  type: null,
  content: null,
  parent_id: null,
  position: null,
  properties: null
)
```

