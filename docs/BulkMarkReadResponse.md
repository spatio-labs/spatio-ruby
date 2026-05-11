# Spatio::BulkMarkReadResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **updated** | **Integer** | Number of messages successfully marked. |  |
| **failed** | [**Array&lt;BulkMarkReadResponseFailedInner&gt;**](BulkMarkReadResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkMarkReadResponse.new(
  updated: null,
  failed: null
)
```

