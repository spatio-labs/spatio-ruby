# Spatio::ExportPDFRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rasterized_slides** | [**Array&lt;ExportPDFRequestRasterizedSlidesInner&gt;**](ExportPDFRequestRasterizedSlidesInner.md) |  | [optional] |
| **theme** | **Hash&lt;String, Object&gt;** | Optional palette override. Schemaless — the export sidecar accepts a free-form palette object. Treat as opaque.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ExportPDFRequest.new(
  rasterized_slides: null,
  theme: null
)
```

