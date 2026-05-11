# Spatio::UpdateTaskRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **due_date** | **Time** |  | [optional] |
| **priority** | **String** |  | [optional] |
| **labels** | **Array&lt;String&gt;** |  | [optional] |
| **tags** | **Array&lt;String&gt;** |  | [optional] |
| **assignee_id** | **String** |  | [optional] |
| **parent_task_id** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateTaskRequest.new(
  title: null,
  description: null,
  status: null,
  due_date: null,
  priority: null,
  labels: null,
  tags: null,
  assignee_id: null,
  parent_task_id: null
)
```

