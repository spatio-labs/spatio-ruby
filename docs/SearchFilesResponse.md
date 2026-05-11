# Spatio::SearchFilesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **files** | [**Array&lt;SpatioFile&gt;**](SpatioFile.md) |  | [optional] |
| **total** | **Integer** |  |  |
| **has_more** | **Boolean** |  |  |
| **query** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SearchFilesResponse.new(
  files: null,
  total: null,
  has_more: null,
  query: null
)
```

