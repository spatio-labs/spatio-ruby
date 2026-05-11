# Spatio::AccountPlan

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tier** | **String** |  |  |
| **display_name** | **String** |  |  |
| **subscription_status** | **String** | Stripe subscription state: &#x60;ACTIVE&#x60;, &#x60;TRIALING&#x60;, &#x60;PAST_DUE&#x60;, &#x60;CANCELED&#x60;, etc. |  |
| **trial_ends_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AccountPlan.new(
  tier: null,
  display_name: null,
  subscription_status: null,
  trial_ends_at: null
)
```

