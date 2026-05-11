# Spatio::SignInMethods

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **has_password** | **Boolean** |  |  |
| **providers** | [**Array&lt;SignInMethodsProvidersInner&gt;**](SignInMethodsProvidersInner.md) |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SignInMethods.new(
  email: null,
  has_password: null,
  providers: null
)
```

