# Spatio::BulkDeleteTasksResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **affected_count** | **Integer** |  |  |
| **task_ids** | **Array&lt;String&gt;** |  |  |
| **failed** | [**Array&lt;BulkDeleteTasksResponseFailedInner&gt;**](BulkDeleteTasksResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkDeleteTasksResponse.new(
  success: null,
  affected_count: null,
  task_ids: null,
  failed: null
)
```

