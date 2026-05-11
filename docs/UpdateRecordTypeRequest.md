# Spatio::UpdateRecordTypeRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **name_plural** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **attribute_schema** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateRecordTypeRequest.new(
  slug: null,
  name: null,
  name_plural: null,
  icon: null,
  attribute_schema: null
)
```

