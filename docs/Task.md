# Spatio::Task

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** | Registered provider id (e.g. &#x60;native-tasks&#x60;, &#x60;linear&#x60;). | [optional] |
| **account_id** | **String** |  | [optional] |
| **owner_user_id** | **String** |  | [optional] |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **status** | **String** | Free-form status string. Canonical values across most providers: &#x60;todo&#x60;, &#x60;in_progress&#x60;, &#x60;in_review&#x60;, &#x60;backlog&#x60;, &#x60;done&#x60;. The platform falls back to &#x60;done&#x60; when &#x60;completed&#x60; is true and &#x60;status&#x60; is empty, else &#x60;todo&#x60;.  | [optional] |
| **completed** | **Boolean** |  |  |
| **due_date** | **Time** |  | [optional] |
| **priority** | **String** | Priority bucket. Canonical values (mapped from a 0–4 integer): &#x60;none&#x60;, &#x60;low&#x60;, &#x60;medium&#x60;, &#x60;high&#x60;, &#x60;urgent&#x60;.  |  |
| **labels** | **Array&lt;String&gt;** |  | [optional] |
| **tags** | **Array&lt;String&gt;** |  | [optional] |
| **assignee_id** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **completed_at** | **Time** |  | [optional] |
| **parent_task_id** | **String** | Parent task id when this is a subtask. | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** | Provider-specific extras. | [optional] |
| **type** | **String** | Discriminator. Canonical values: &#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;. Empty defaults to &#x60;todo&#x60;.  | [optional] |
| **source_platform** | **String** | When this task was auto-generated from another artifact (e.g. a calendar event reminder), the platform id of that artifact.  | [optional] |
| **source_id** | **String** | Source artifact id paired with &#x60;sourcePlatform&#x60;. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Task.new(
  id: null,
  provider: null,
  account_id: null,
  owner_user_id: null,
  title: null,
  description: null,
  status: null,
  completed: null,
  due_date: null,
  priority: null,
  labels: null,
  tags: null,
  assignee_id: null,
  created_at: null,
  updated_at: null,
  completed_at: null,
  parent_task_id: null,
  metadata: null,
  type: null,
  source_platform: null,
  source_id: null
)
```

