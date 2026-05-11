# Spatio::AccountListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **accounts_by_platform** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **total_accounts** | **Integer** |  | [optional] |
| **accounts** | **Array&lt;Hash&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AccountListResponse.new(
  accounts_by_platform: null,
  total_accounts: null,
  accounts: null
)
```

