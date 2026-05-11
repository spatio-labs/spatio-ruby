# Spatio::BulkUpdateTasksRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **task_ids** | **Array&lt;String&gt;** |  |  |
| **account_ids** | **Array&lt;String&gt;** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **updates** | [**UpdateTaskRequest**](UpdateTaskRequest.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkUpdateTasksRequest.new(
  task_ids: null,
  account_ids: null,
  account_id: null,
  updates: null
)
```

