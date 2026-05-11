# Spatio::DownloadFileResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **signed_url** | **String** | Pre-signed direct-download URL pointing at the backing storage (R2, Drive, etc.). Time-limited per provider. Clients follow the URL — the platform does not proxy bytes.  |  |
| **file** | [**SpatioFile**](SpatioFile.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::DownloadFileResponse.new(
  signed_url: null,
  file: null
)
```

