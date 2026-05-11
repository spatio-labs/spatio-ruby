# Spatio::SpatioFile

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **size** | **Integer** | Bytes. |  |
| **mime_type** | **String** |  |  |
| **folder_id** | **String** |  | [optional] |
| **storage_type** | **String** | Backing storage class — &#x60;r2&#x60;, &#x60;gdrive&#x60;, &#x60;dropbox&#x60;, etc. Provider-specific; treat as opaque.  |  |
| **download_url** | **String** | Pre-signed download URL when one is cached on the row. Use &#x60;GET /v1/files/{id}/download&#x60; for a guaranteed-fresh URL — this field can lag past expiry.  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SpatioFile.new(
  id: null,
  provider: null,
  account_id: null,
  name: null,
  size: null,
  mime_type: null,
  folder_id: null,
  storage_type: null,
  download_url: null,
  metadata: null,
  created_at: null,
  updated_at: null
)
```

