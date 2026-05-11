# Spatio::UpdateSheetRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **data** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **row_count** | **Integer** |  | [optional] |
| **column_count** | **Integer** |  | [optional] |
| **is_public** | **Boolean** |  | [optional] |
| **is_read_only** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateSheetRequest.new(
  name: null,
  description: null,
  data: null,
  row_count: null,
  column_count: null,
  is_public: null,
  is_read_only: null
)
```

