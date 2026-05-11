# Spatio::ChangePasswordRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **current_password** | **String** | Required when the account already has a password set; omit on first-set. | [optional] |
| **new_password** | **String** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ChangePasswordRequest.new(
  current_password: null,
  new_password: null
)
```

