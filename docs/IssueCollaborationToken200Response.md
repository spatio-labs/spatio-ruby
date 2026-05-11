# Spatio::IssueCollaborationToken200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | HS256 JWT, signed with the shared platform/worker secret. |  |
| **ws_url** | **String** | Base WebSocket URL of the Yjs worker. |  |
| **room** | **String** |  | [optional] |
| **expires_at** | **Time** |  |  |
| **expires_in** | **Integer** | Seconds until the token expires. |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::IssueCollaborationToken200Response.new(
  token: null,
  ws_url: wss://realtime-collaboration.matthew-b2d.workers.dev,
  room: null,
  expires_at: null,
  expires_in: null
)
```

