# Spatio::ChunkedFileManifest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **manifest_id** | **String** |  |  |
| **file_id** | **String** |  |  |
| **file_name** | **String** |  |  |
| **version** | **Integer** |  |  |
| **total_size** | **Integer** |  |  |
| **block_count** | **Integer** |  |  |
| **chunking_algorithm** | **String** |  | [optional] |
| **file_checksum** | **String** |  | [optional] |
| **blocks** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ChunkedFileManifest.new(
  manifest_id: null,
  file_id: null,
  file_name: null,
  version: null,
  total_size: null,
  block_count: null,
  chunking_algorithm: null,
  file_checksum: null,
  blocks: null
)
```

