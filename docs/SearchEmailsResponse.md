# Spatio::SearchEmailsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **emails** | [**Array&lt;Email&gt;**](Email.md) | &#x60;null&#x60; when there are no results (Go nil-slice serialization). Treat as equivalent to an empty array.  | [optional] |
| **total** | **Integer** |  |  |
| **next_page_token** | **String** |  | [optional] |
| **provider** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SearchEmailsResponse.new(
  emails: null,
  total: null,
  next_page_token: null,
  provider: null
)
```

