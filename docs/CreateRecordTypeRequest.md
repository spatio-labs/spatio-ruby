# Spatio::CreateRecordTypeRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **organization_id** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **name_plural** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **attribute_schema** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateRecordTypeRequest.new(
  organization_id: null,
  slug: null,
  name: null,
  name_plural: null,
  icon: null,
  attribute_schema: null
)
```

