# Spatio::SendChatMessageResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **message_id** | **String** |  |  |
| **channel_id** | **String** |  | [optional] |
| **thread_id** | **String** |  | [optional] |
| **provider** | **String** |  |  |
| **error** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SendChatMessageResponse.new(
  success: null,
  message_id: null,
  channel_id: null,
  thread_id: null,
  provider: null,
  error: null
)
```

