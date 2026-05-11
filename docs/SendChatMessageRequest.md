# Spatio::SendChatMessageRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **channel** | **String** | Channel or DM id (provider-scoped). |  |
| **text** | **String** |  |  |
| **thread_id** | **String** |  | [optional] |
| **blocks** | **Array&lt;Hash&lt;String, Object&gt;&gt;** | Provider-specific rich-message blocks. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SendChatMessageRequest.new(
  account_id: null,
  channel: null,
  text: null,
  thread_id: null,
  blocks: null
)
```

