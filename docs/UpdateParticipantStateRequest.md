# Spatio::UpdateParticipantStateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **audio_enabled** | **Boolean** |  | [optional] |
| **video_enabled** | **Boolean** |  | [optional] |
| **screen_share_enabled** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateParticipantStateRequest.new(
  audio_enabled: null,
  video_enabled: null,
  screen_share_enabled: null
)
```

