# Spatio::ListDraftsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **drafts** | [**Array&lt;Draft&gt;**](Draft.md) |  |  |
| **total** | **Integer** |  |  |
| **next_page_token** | **String** |  | [optional] |
| **provider** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ListDraftsResponse.new(
  drafts: null,
  total: null,
  next_page_token: null,
  provider: null
)
```

