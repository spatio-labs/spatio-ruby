# Spatio::Record

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **organization_id** | **String** |  | [optional] |
| **record_type_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **attributes** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Record.new(
  id: null,
  organization_id: null,
  record_type_id: null,
  name: null,
  attributes: null,
  metadata: null,
  created_at: null,
  updated_at: null
)
```

