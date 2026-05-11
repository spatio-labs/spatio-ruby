# Spatio::BulkUpdateTasksResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **affected_count** | **Integer** |  |  |
| **tasks** | [**Array&lt;Task&gt;**](Task.md) |  |  |
| **failed** | [**Array&lt;BulkDeleteTasksResponseFailedInner&gt;**](BulkDeleteTasksResponseFailedInner.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkUpdateTasksResponse.new(
  success: null,
  affected_count: null,
  tasks: null,
  failed: null
)
```

