# Spatio::BlockContent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rich_text** | [**Array&lt;RichTextObject&gt;**](RichTextObject.md) |  | [optional] |
| **language** | **String** | Programming language for &#x60;code&#x60; blocks. | [optional] |
| **checked** | **Boolean** | Toggle state for &#x60;to_do&#x60; blocks. | [optional] |
| **icon** | **String** | Emoji or short string for &#x60;callout&#x60; blocks. | [optional] |
| **color** | **String** | Theme color for &#x60;callout&#x60; blocks. | [optional] |
| **url** | **String** | Source URL for &#x60;image&#x60;, &#x60;video&#x60;, &#x60;file&#x60; blocks. | [optional] |
| **caption** | **String** | Visible caption for media blocks. | [optional] |
| **alt_text** | **String** | Screen-reader description for media blocks. Distinct from &#x60;caption&#x60; (visible to readers) — required for accessible notes when the image conveys meaning.  | [optional] |
| **embed_url** | **String** | Source URL for &#x60;embed&#x60; blocks. | [optional] |
| **cells** | **Array&lt;Array&lt;RichTextObject&gt;&gt;** | 2D rich-text grid for &#x60;table&#x60; and &#x60;table_row&#x60; blocks. | [optional] |
| **expression** | **String** | TeX/MathJax expression for &#x60;equation&#x60; blocks. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BlockContent.new(
  rich_text: null,
  language: null,
  checked: null,
  icon: null,
  color: null,
  url: null,
  caption: null,
  alt_text: null,
  embed_url: null,
  cells: null,
  expression: null
)
```

