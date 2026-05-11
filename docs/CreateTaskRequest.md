# Spatio::CreateTaskRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **due_date** | **Time** |  | [optional] |
| **priority** | **String** |  | [optional] |
| **labels** | **Array&lt;String&gt;** |  | [optional] |
| **tags** | **Array&lt;String&gt;** |  | [optional] |
| **assignee_id** | **String** |  | [optional] |
| **parent_task_id** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |
| **source_platform** | **String** |  | [optional] |
| **source_id** | **String** |  | [optional] |
| **account_id** | **String** | Optional override for the target connected account. May also be passed as &#x60;?accountId&#x3D;&#x60;.  | [optional] |
| **provider** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateTaskRequest.new(
  title: null,
  description: null,
  status: null,
  due_date: null,
  priority: null,
  labels: null,
  tags: null,
  assignee_id: null,
  parent_task_id: null,
  type: null,
  source_platform: null,
  source_id: null,
  account_id: null,
  provider: null
)
```

