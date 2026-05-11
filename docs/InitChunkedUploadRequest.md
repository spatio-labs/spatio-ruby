# Spatio::InitChunkedUploadRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_name** | **String** |  |  |
| **total_size** | **Integer** |  |  |
| **mime_type** | **String** |  |  |
| **expected_blocks** | **Array&lt;String&gt;** | Hashes of every block the client intends to upload. |  |
| **folder_id** | **String** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::InitChunkedUploadRequest.new(
  file_name: null,
  total_size: null,
  mime_type: null,
  expected_blocks: null,
  folder_id: null,
  workspace_id: null,
  organization_id: null
)
```

