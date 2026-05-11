# Spatio::CreateCalendarEvent201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **data** | [**SpatioEvent**](SpatioEvent.md) |  | [optional] |
| **errors** | [**Array&lt;CalendarAccountError&gt;**](CalendarAccountError.md) |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateCalendarEvent201Response.new(
  success: null,
  data: null,
  errors: null,
  metadata: null
)
```

