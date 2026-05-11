# Spatio::ProposeRecommendationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  | [optional] |
| **kind** | **String** |  |  |
| **title** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **payload** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ProposeRecommendationRequest.new(
  workspace_id: null,
  kind: null,
  title: null,
  body: null,
  payload: null,
  expires_at: null
)
```

