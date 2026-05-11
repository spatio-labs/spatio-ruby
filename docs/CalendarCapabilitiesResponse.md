# Spatio::CalendarCapabilitiesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  |  |
| **provider_id** | **String** |  |  |
| **capabilities** | **Hash&lt;String, Object&gt;** | Per-account feature gate. The renderer reads these to enable/ disable form fields (recurrence pickers, attendee inputs, etc.) based on what the underlying provider supports.  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CalendarCapabilitiesResponse.new(
  account_id: null,
  provider_id: null,
  capabilities: null
)
```

