# Spatio::UpdateNoteRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  | [optional] |
| **content** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **cover_image** | **String** |  | [optional] |
| **parent_id** | **String** |  | [optional] |
| **properties** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **archived** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateNoteRequest.new(
  title: null,
  content: null,
  icon: null,
  cover_image: null,
  parent_id: null,
  properties: null,
  archived: null
)
```

