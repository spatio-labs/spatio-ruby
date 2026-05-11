# Spatio::InitChunkedUploadResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **session_id** | **String** |  |  |
| **blocks_to_upload** | **Array&lt;String&gt;** |  |  |
| **blocks_already_exist** | **Array&lt;String&gt;** | Blocks the platform already has and the client can skip (content-addressed deduplication).  |  |
| **deduplication_pct** | **Float** |  |  |
| **estimated_upload_size** | **Integer** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::InitChunkedUploadResponse.new(
  session_id: null,
  blocks_to_upload: null,
  blocks_already_exist: null,
  deduplication_pct: null,
  estimated_upload_size: null
)
```

