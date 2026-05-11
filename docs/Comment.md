# Spatio::Comment

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **note_id** | **String** |  |  |
| **parent_comment_id** | **String** |  | [optional] |
| **block_id** | **String** |  | [optional] |
| **body** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **author** | [**CommentAuthor**](CommentAuthor.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Comment.new(
  id: null,
  note_id: null,
  parent_comment_id: null,
  block_id: null,
  body: null,
  created_at: null,
  updated_at: null,
  author: null
)
```

