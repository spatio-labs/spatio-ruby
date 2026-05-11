# Spatio::BulkDeleteEmailsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **message_ids** | **Array&lt;String&gt;** |  |  |
| **permanent** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkDeleteEmailsRequest.new(
  account_id: null,
  message_ids: null,
  permanent: null
)
```

