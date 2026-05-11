# Spatio::BulkMarkReadRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **message_ids** | **Array&lt;String&gt;** |  |  |
| **read** | **Boolean** |  | [optional][default to true] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::BulkMarkReadRequest.new(
  account_id: null,
  message_ids: null,
  read: null
)
```

