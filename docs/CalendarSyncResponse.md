# Spatio::CalendarSyncResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enqueued** | **Integer** |  |  |
| **jobs** | **Array&lt;String&gt;** |  |  |
| **waited** | **Boolean** |  | [optional] |
| **timed_out** | **Boolean** |  | [optional] |
| **errors** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CalendarSyncResponse.new(
  enqueued: null,
  jobs: null,
  waited: null,
  timed_out: null,
  errors: null
)
```

