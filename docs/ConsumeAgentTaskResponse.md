# Spatio::ConsumeAgentTaskResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **allowed** | **Boolean** |  |  |
| **task_count** | **Integer** |  | [optional] |
| **daily_limit** | **Integer** |  | [optional] |
| **trial_ends_at** | **Time** |  | [optional] |
| **paid** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ConsumeAgentTaskResponse.new(
  allowed: null,
  task_count: null,
  daily_limit: null,
  trial_ends_at: null,
  paid: null
)
```

