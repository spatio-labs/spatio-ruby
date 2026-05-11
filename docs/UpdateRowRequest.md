# Spatio::UpdateRowRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **cells** | **Hash&lt;String, Object&gt;** | Sparse update. Keys present in the map overwrite that column; keys absent are preserved.  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateRowRequest.new(
  cells: null
)
```

