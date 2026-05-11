# Spatio::RoutineRun

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **routine_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **progress** | **Integer** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **completed_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::RoutineRun.new(
  id: null,
  routine_id: null,
  status: null,
  progress: null,
  metadata: null,
  started_at: null,
  completed_at: null
)
```

