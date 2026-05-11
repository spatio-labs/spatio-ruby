# Spatio::RichTextObject

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  |  |
| **text** | **String** |  | [optional] |
| **annotations** | [**TextAnnotations**](TextAnnotations.md) |  | [optional] |
| **href** | **String** | External URL (&#x60;https://…&#x60;) or internal note anchor (&#x60;#blockId&#x60;, &#x60;#heading-slug&#x60;). Internal anchors resolve to the matching block in the same note.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::RichTextObject.new(
  type: null,
  text: null,
  annotations: null,
  href: null
)
```

