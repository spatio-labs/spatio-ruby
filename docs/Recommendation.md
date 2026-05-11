# Spatio::Recommendation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **workspace_id** | **String** |  | [optional] |
| **user_id** | **String** |  | [optional] |
| **kind** | **String** | Provider-tagged proposal kind (e.g. &#x60;note.draft&#x60;, &#x60;task.followup&#x60;). | [optional] |
| **title** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **status** | **String** |  |  |
| **payload** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Recommendation.new(
  id: null,
  workspace_id: null,
  user_id: null,
  kind: null,
  title: null,
  body: null,
  status: null,
  payload: null,
  created_at: null,
  updated_at: null,
  expires_at: null
)
```

