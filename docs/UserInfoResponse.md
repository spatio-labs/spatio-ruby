# Spatio::UserInfoResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sub** | **String** | User identifier (stable for the lifetime of the user). |  |
| **email** | **String** |  | [optional] |
| **email_verified** | **Boolean** |  | [optional] |
| **name** | **String** |  | [optional] |
| **given_name** | **String** |  | [optional] |
| **family_name** | **String** |  | [optional] |
| **preferred_username** | **String** |  | [optional] |
| **picture** | **String** |  | [optional] |
| **updated_at** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UserInfoResponse.new(
  sub: null,
  email: null,
  email_verified: null,
  name: null,
  given_name: null,
  family_name: null,
  preferred_username: null,
  picture: null,
  updated_at: null
)
```

