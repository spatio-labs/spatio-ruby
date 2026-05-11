# Spatio::SendEmailResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **message_id** | **String** |  |  |
| **thread_id** | **String** |  | [optional] |
| **provider** | **String** |  |  |
| **error** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SendEmailResponse.new(
  success: null,
  message_id: null,
  thread_id: null,
  provider: null,
  error: null
)
```

