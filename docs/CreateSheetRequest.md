# Spatio::CreateSheetRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **data** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **row_count** | **Integer** |  | [optional] |
| **column_count** | **Integer** |  | [optional] |
| **account_id** | **String** | Optional override for the target connected account. May also be passed as &#x60;?accountId&#x3D;&#x60;.  | [optional] |
| **provider** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateSheetRequest.new(
  name: null,
  description: null,
  data: null,
  row_count: null,
  column_count: null,
  account_id: null,
  provider: null
)
```

