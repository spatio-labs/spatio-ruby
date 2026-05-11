# Spatio::MoveBlockRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **parent_id** | **String** | New parent block id; omit to keep the current parent. | [optional] |
| **position** | **Integer** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::MoveBlockRequest.new(
  parent_id: null,
  position: null
)
```

