# Spatio::ExportPDFR2Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **storage** | **String** |  |  |
| **url** | **String** | 24-hour signed URL. |  |
| **expires_at** | **Time** |  |  |
| **size** | **Integer** | PDF size in bytes. |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ExportPDFR2Response.new(
  storage: null,
  url: null,
  expires_at: null,
  size: null
)
```

