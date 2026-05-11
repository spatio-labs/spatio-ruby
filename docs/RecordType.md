# Spatio::RecordType

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **organization_id** | **String** |  |  |
| **slug** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **name_plural** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **attribute_schema** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::RecordType.new(
  id: null,
  organization_id: null,
  slug: null,
  name: null,
  name_plural: null,
  icon: null,
  attribute_schema: null,
  created_at: null,
  updated_at: null
)
```

