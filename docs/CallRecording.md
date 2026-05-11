# Spatio::CallRecording

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **call_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **ended_at** | **Time** |  | [optional] |
| **url** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CallRecording.new(
  id: null,
  call_id: null,
  status: null,
  started_at: null,
  ended_at: null,
  url: null,
  metadata: null
)
```

