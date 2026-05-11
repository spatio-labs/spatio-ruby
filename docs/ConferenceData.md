# Spatio::ConferenceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  |  |
| **uri** | **String** |  |  |
| **meeting_id** | **String** |  | [optional] |
| **passcode** | **String** |  | [optional] |
| **access_code** | **String** |  | [optional] |
| **dial_in** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ConferenceData.new(
  type: null,
  uri: null,
  meeting_id: null,
  passcode: null,
  access_code: null,
  dial_in: null
)
```

