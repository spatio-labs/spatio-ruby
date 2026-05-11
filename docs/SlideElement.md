# Spatio::SlideElement

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **slide_id** | **String** |  |  |
| **element_type** | **String** | Free-form type id (&#x60;text&#x60;, &#x60;image&#x60;, &#x60;shape&#x60;, etc.). |  |
| **content** | **Hash&lt;String, Object&gt;** |  |  |
| **x** | **Float** |  |  |
| **y** | **Float** |  |  |
| **width** | **Float** |  |  |
| **height** | **Float** |  |  |
| **rotation** | **Float** | Degrees. |  |
| **z_index** | **Integer** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SlideElement.new(
  id: null,
  slide_id: null,
  element_type: null,
  content: null,
  x: null,
  y: null,
  width: null,
  height: null,
  rotation: null,
  z_index: null,
  created_at: null,
  updated_at: null
)
```

