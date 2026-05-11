# Spatio::Block

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **note_id** | **String** |  |  |
| **parent_id** | **String** |  | [optional] |
| **type** | [**BlockType**](BlockType.md) |  |  |
| **content** | [**BlockContent**](BlockContent.md) |  |  |
| **properties** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **position** | **Integer** | Order within the parent (0-indexed). |  |
| **has_children** | **Boolean** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Block.new(
  id: null,
  note_id: null,
  parent_id: null,
  type: null,
  content: null,
  properties: null,
  position: null,
  has_children: null,
  created_at: null,
  updated_at: null
)
```

