# Spatio::Routine

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **workspace_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **schedule** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **status** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Routine.new(
  id: null,
  workspace_id: null,
  name: null,
  description: null,
  schedule: null,
  status: null,
  metadata: null,
  created_at: null,
  updated_at: null
)
```

