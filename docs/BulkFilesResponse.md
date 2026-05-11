# Spatio::BulkFilesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **affected_count** | **Integer** |  |  |
| **file_ids** | **Array&lt;String&gt;** |  |  |
| **failed** | [**Array&lt;BulkFilesResponseFailedInner&gt;**](BulkFilesResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkFilesResponse.new(
  success: null,
  affected_count: null,
  file_ids: null,
  failed: null
)
```

