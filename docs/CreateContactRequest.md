# Spatio::CreateContactRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **first_name** | **String** |  | [optional] |
| **last_name** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **phone** | **String** |  | [optional] |
| **company** | **String** |  | [optional] |
| **title** | **String** |  | [optional] |
| **notes** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateContactRequest.new(
  first_name: null,
  last_name: null,
  email: null,
  phone: null,
  company: null,
  title: null,
  notes: null,
  metadata: null
)
```

