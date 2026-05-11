# Spatio::ListMessagesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **messages** | [**Array&lt;ChatMessage&gt;**](ChatMessage.md) |  | [optional] |
| **has_more** | **Boolean** |  |  |
| **next_cursor** | **String** |  | [optional] |
| **provider** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListMessagesResponse.new(
  messages: null,
  has_more: null,
  next_cursor: null,
  provider: null
)
```

