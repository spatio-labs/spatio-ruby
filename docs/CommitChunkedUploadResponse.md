# Spatio::CommitChunkedUploadResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **file_id** | **String** |  |  |
| **manifest_id** | **String** |  |  |
| **version** | **Integer** |  |  |
| **total_size** | **Integer** |  |  |
| **physical_size** | **Integer** |  | [optional] |
| **deduplication_pct** | **Float** |  | [optional] |
| **total_blocks** | **Integer** |  | [optional] |
| **new_blocks** | **Integer** |  | [optional] |
| **deduplicated_blocks** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CommitChunkedUploadResponse.new(
  success: null,
  file_id: null,
  manifest_id: null,
  version: null,
  total_size: null,
  physical_size: null,
  deduplication_pct: null,
  total_blocks: null,
  new_blocks: null,
  deduplicated_blocks: null
)
```

