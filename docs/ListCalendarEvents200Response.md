# Spatio::ListCalendarEvents200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **data** | [**ListEventsData**](ListEventsData.md) |  | [optional] |
| **errors** | [**Array&lt;CalendarAccountError&gt;**](CalendarAccountError.md) |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListCalendarEvents200Response.new(
  success: null,
  data: null,
  errors: null,
  metadata: null
)
```

