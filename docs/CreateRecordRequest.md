# Spatio::CreateRecordRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **organization_id** | **String** |  | [optional] |
| **record_type_id** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **attributes** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateRecordRequest.new(
  organization_id: null,
  record_type_id: null,
  name: null,
  attributes: null,
  metadata: null
)
```

