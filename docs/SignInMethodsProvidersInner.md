# Spatio::SignInMethodsProvidersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** | OAuth IdP: &#x60;GOOGLE&#x60;, &#x60;GITHUB&#x60;, etc. |  |
| **account_email** | **String** |  | [optional] |
| **linked_at** | **Time** |  | [optional] |
| **last_used_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SignInMethodsProvidersInner.new(
  provider: null,
  account_email: null,
  linked_at: null,
  last_used_at: null
)
```

