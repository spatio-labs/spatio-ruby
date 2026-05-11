# Spatio::CreateOrganizationInvitationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **role** | **String** |  |  |
| **workspace_id** | **String** | Optional — the invitee will also be added to this workspace on accept. Defaults to the org&#39;s default workspace.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateOrganizationInvitationRequest.new(
  email: null,
  role: null,
  workspace_id: null
)
```

