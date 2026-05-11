# Spatio::CreateEventRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  |  |
| **calendar_id** | **String** | Specific calendar within the account; omit for the default. | [optional] |
| **event** | [**SpatioEvent**](SpatioEvent.md) |  |  |
| **send_updates** | **String** | Notification policy passed through to the provider. | [optional] |
| **conference_type** | **String** | When set, the platform will auto-attach a conference link of the matching type (&#x60;spatio&#x60;, &#x60;meet&#x60;, &#x60;zoom&#x60;, &#x60;teams&#x60;).  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateEventRequest.new(
  account_id: null,
  calendar_id: null,
  event: null,
  send_updates: null,
  conference_type: null
)
```

