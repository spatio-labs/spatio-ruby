# Spatio::UploadChunkedBlockResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **block_hash** | **String** |  |  |
| **uploaded** | **Boolean** |  |  |
| **blocks_remaining** | **Integer** |  |  |
| **progress** | **Float** | Percent complete, 0–100. |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UploadChunkedBlockResponse.new(
  block_hash: null,
  uploaded: null,
  blocks_remaining: null,
  progress: null
)
```

