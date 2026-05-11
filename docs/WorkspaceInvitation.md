# Spatio::WorkspaceInvitation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **workspace_id** | **String** |  | [optional] |
| **email** | **String** |  |  |
| **role** | **String** |  |  |
| **expires_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **accepted_at** | **Time** |  | [optional] |
| **revoked_at** | **Time** |  | [optional] |
| **status** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::WorkspaceInvitation.new(
  id: null,
  workspace_id: null,
  email: null,
  role: null,
  expires_at: null,
  created_at: null,
  accepted_at: null,
  revoked_at: null,
  status: null
)
```

