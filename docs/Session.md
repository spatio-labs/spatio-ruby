# Spatio::Session

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **ip_address** | **String** |  | [optional] |
| **user_agent** | **String** |  | [optional] |
| **device_type** | **String** |  | [optional] |
| **browser** | **String** |  | [optional] |
| **os** | **String** |  | [optional] |
| **country** | **String** |  | [optional] |
| **city** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **last_active_at** | **Time** |  | [optional] |
| **is_current** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Session.new(
  id: null,
  ip_address: null,
  user_agent: null,
  device_type: null,
  browser: null,
  os: null,
  country: null,
  city: null,
  created_at: null,
  last_active_at: null,
  is_current: null
)
```

