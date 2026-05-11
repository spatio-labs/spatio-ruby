# Spatio::CreateRowRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **index** | **Integer** | Optional zero-based insert position. Omit to append at the end.  | [optional] |
| **cells** | **Hash&lt;String, Object&gt;** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateRowRequest.new(
  index: null,
  cells: null
)
```

