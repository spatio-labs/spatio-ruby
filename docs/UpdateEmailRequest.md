# Spatio::UpdateEmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **is_read** | **Boolean** |  | [optional] |
| **is_starred** | **Boolean** |  | [optional] |
| **add_labels** | **Array&lt;String&gt;** |  | [optional] |
| **remove_labels** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateEmailRequest.new(
  account_id: null,
  is_read: null,
  is_starred: null,
  add_labels: null,
  remove_labels: null
)
```

