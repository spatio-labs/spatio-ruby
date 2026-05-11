# Spatio::BulkDeleteTasksRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **task_ids** | **Array&lt;String&gt;** |  | [optional] |
| **account_ids** | **Array&lt;String&gt;** | Parallel slice with taskIds — accountIds[i] targets taskIds[i]. | [optional] |
| **task_id** | **String** | Singular fallback when only deleting one task. | [optional] |
| **account_id** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkDeleteTasksRequest.new(
  task_ids: null,
  account_ids: null,
  task_id: null,
  account_id: null
)
```

