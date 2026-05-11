# Spatio::ChatMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **channel_id** | **String** |  |  |
| **user_id** | **String** |  |  |
| **text** | **String** |  |  |
| **thread_id** | **String** | Set on replies and on parent messages once a thread exists.  | [optional] |
| **timestamp** | **Time** |  |  |
| **reply_count** | **Integer** |  | [optional] |
| **extra** | **Hash&lt;String, Object&gt;** | Provider-specific extras. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ChatMessage.new(
  id: null,
  provider: null,
  account_id: null,
  channel_id: null,
  user_id: null,
  text: null,
  thread_id: null,
  timestamp: null,
  reply_count: null,
  extra: null
)
```

