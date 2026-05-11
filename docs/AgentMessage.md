# Spatio::AgentMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **conversation_id** | **String** |  | [optional] |
| **role** | **String** |  |  |
| **content** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AgentMessage.new(
  id: null,
  conversation_id: null,
  role: null,
  content: null,
  metadata: null,
  created_at: null
)
```

