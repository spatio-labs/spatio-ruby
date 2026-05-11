# Spatio::ListChatUsersResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **users** | [**Array&lt;ChatUser&gt;**](ChatUser.md) |  | [optional] |
| **total** | **Integer** |  |  |
| **next_cursor** | **String** |  | [optional] |
| **provider** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListChatUsersResponse.new(
  users: null,
  total: null,
  next_cursor: null,
  provider: null
)
```

