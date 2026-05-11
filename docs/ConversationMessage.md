# Spatio::ConversationMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **conversation_id** | **String** |  |  |
| **role** | **String** | &#x60;user&#x60;, &#x60;assistant&#x60;, &#x60;system&#x60;, or &#x60;tool&#x60;. |  |
| **content** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ConversationMessage.new(
  id: null,
  conversation_id: null,
  role: null,
  content: null,
  metadata: null,
  created_at: null
)
```

