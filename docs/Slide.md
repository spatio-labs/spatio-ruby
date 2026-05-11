# Spatio::Slide

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **presentation_id** | **String** |  |  |
| **title** | **String** |  |  |
| **notes** | **String** | Speaker notes. | [optional] |
| **layout** | **String** | Free-form layout id. Provider-specific (&#x60;title&#x60;, &#x60;two-column&#x60;, &#x60;image-left&#x60;, custom). Not enumerated to avoid forcing a breaking change every time a provider adds one.  | [optional] |
| **background_color** | **String** |  | [optional] |
| **background_image_url** | **String** |  | [optional] |
| **text_color** | **String** |  | [optional] |
| **transition** | **String** | Free-form transition id. | [optional] |
| **position** | **Integer** | Zero-based position within the presentation. |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Slide.new(
  id: null,
  provider: null,
  account_id: null,
  presentation_id: null,
  title: null,
  notes: null,
  layout: null,
  background_color: null,
  background_image_url: null,
  text_color: null,
  transition: null,
  position: null,
  created_at: null,
  updated_at: null
)
```

