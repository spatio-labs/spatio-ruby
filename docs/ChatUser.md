# Spatio::ChatUser

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **real_name** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **avatar** | **String** |  | [optional] |
| **is_bot** | **Boolean** |  |  |
| **is_active** | **Boolean** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ChatUser.new(
  id: null,
  provider: null,
  account_id: null,
  name: null,
  real_name: null,
  email: null,
  avatar: null,
  is_bot: null,
  is_active: null
)
```

