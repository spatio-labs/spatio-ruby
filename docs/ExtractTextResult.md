# Spatio::ExtractTextResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **text** | **String** |  |  |
| **page_count** | **Integer** |  |  |
| **pages** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **truncated** | **Boolean** | &#x60;true&#x60; when &#x60;maxChars&#x60; was hit before the end. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ExtractTextResult.new(
  text: null,
  page_count: null,
  pages: null,
  truncated: null
)
```

