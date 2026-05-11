# Spatio::CreateRoutineRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **schedule** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateRoutineRequest.new(
  workspace_id: null,
  name: null,
  description: null,
  schedule: null,
  metadata: null
)
```

