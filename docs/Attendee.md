# Spatio::Attendee

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **status** | [**AttendeeStatus**](AttendeeStatus.md) |  |  |
| **role** | [**AttendeeRole**](AttendeeRole.md) |  |  |
| **optional** | **Boolean** | Legacy boolean — superseded by &#x60;role&#x60; (&#x60;role: optional&#x60; carries the same signal). Kept on the wire for client compatibility.  |  |
| **comment** | **String** |  | [optional] |
| **additional_guests** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Attendee.new(
  email: null,
  name: null,
  status: null,
  role: null,
  optional: null,
  comment: null,
  additional_guests: null
)
```

