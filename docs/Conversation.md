# Spatio::Conversation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **title** | **String** |  |  |
| **context** | **String** | Free-form context tag (e.g. &#x60;sidebar:sheets:entity:&lt;id&gt;&#x60;). | [optional] |
| **cwd** | **String** |  | [optional] |
| **session_id** | **String** |  | [optional] |
| **pinned** | **Boolean** |  | [optional] |
| **last_message_at** | **Time** |  | [optional] |
| **message_count** | **Integer** |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Conversation.new(
  id: null,
  user_id: null,
  title: null,
  context: null,
  cwd: null,
  session_id: null,
  pinned: null,
  last_message_at: null,
  message_count: null,
  is_active: null,
  metadata: null,
  created_at: null,
  updated_at: null
)
```

