# Spatio::ListEventsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **events** | [**Array&lt;SpatioEvent&gt;**](SpatioEvent.md) | &#x60;null&#x60; when there are no results (Go nil-slice serialization).  | [optional] |
| **next_page_token** | **String** |  | [optional] |
| **total_results** | **Integer** |  | [optional] |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListEventsData.new(
  events: null,
  next_page_token: null,
  total_results: null,
  updated_at: null
)
```

