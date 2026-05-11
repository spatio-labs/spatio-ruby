# Spatio::ListChannelsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **channels** | [**Array&lt;Channel&gt;**](Channel.md) | &#x60;null&#x60; when no results (Go nil-slice serialization). | [optional] |
| **total** | **Integer** |  |  |
| **next_cursor** | **String** |  | [optional] |
| **provider** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListChannelsResponse.new(
  channels: null,
  total: null,
  next_cursor: null,
  provider: null
)
```

