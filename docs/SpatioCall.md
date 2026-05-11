# Spatio::SpatioCall

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **title** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **host_user_id** | **String** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **room_id** | **String** |  | [optional] |
| **participants** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **ended_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SpatioCall.new(
  id: null,
  title: null,
  status: null,
  host_user_id: null,
  workspace_id: null,
  room_id: null,
  participants: null,
  metadata: null,
  started_at: null,
  ended_at: null,
  created_at: null
)
```

