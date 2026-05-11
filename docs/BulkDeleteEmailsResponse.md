# Spatio::BulkDeleteEmailsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **deleted** | **Array&lt;String&gt;** |  |  |
| **failed** | [**Array&lt;BulkArchiveResponseFailedInner&gt;**](BulkArchiveResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkDeleteEmailsResponse.new(
  success: null,
  deleted: null,
  failed: null
)
```

