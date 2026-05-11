# Spatio::BulkMoveFilesRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_ids** | **Array&lt;String&gt;** |  | [optional] |
| **account_ids** | **Array&lt;String&gt;** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **target_folder_id** | **String** |  | [optional] |
| **folder_id** | **String** | Alias for &#x60;targetFolderId&#x60;. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkMoveFilesRequest.new(
  file_ids: null,
  account_ids: null,
  account_id: null,
  target_folder_id: null,
  folder_id: null
)
```

