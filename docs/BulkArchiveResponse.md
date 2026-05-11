# Spatio::BulkArchiveResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** | &#x60;true&#x60; only when zero rows in &#x60;failed&#x60;. |  |
| **archived** | **Array&lt;String&gt;** |  |  |
| **failed** | [**Array&lt;BulkArchiveResponseFailedInner&gt;**](BulkArchiveResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkArchiveResponse.new(
  success: null,
  archived: null,
  failed: null
)
```

