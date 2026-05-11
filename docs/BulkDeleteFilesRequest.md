# Spatio::BulkDeleteFilesRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_ids** | **Array&lt;String&gt;** |  | [optional] |
| **account_ids** | **Array&lt;String&gt;** | Parallel slice with fileIds — accountIds[i] targets fileIds[i]. | [optional] |
| **file_id** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkDeleteFilesRequest.new(
  file_ids: null,
  account_ids: null,
  file_id: null,
  account_id: null
)
```

