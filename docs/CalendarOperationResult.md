# Spatio::CalendarOperationResult

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **data** | **Object** | Operation-specific payload. See the operation&#39;s response description for the concrete shape.  | [optional] |
| **errors** | [**Array&lt;CalendarAccountError&gt;**](CalendarAccountError.md) |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CalendarOperationResult.new(
  success: null,
  data: null,
  errors: null,
  metadata: null
)
```

