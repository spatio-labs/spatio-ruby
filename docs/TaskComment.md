# Spatio::TaskComment

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **task_id** | **String** |  |  |
| **content** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **author** | [**TaskCommentAuthor**](TaskCommentAuthor.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::TaskComment.new(
  id: null,
  task_id: null,
  content: null,
  created_at: null,
  updated_at: null,
  author: null
)
```

