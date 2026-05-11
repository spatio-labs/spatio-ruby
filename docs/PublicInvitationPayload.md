# Spatio::PublicInvitationPayload

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **kind** | **String** |  |  |
| **id** | **String** |  |  |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **email** | **String** |  |  |
| **role** | **String** |  |  |
| **status** | **String** |  |  |
| **expires_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **workspace** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **organization** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **invited_by** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::PublicInvitationPayload.new(
  kind: null,
  id: null,
  workspace_id: null,
  organization_id: null,
  email: null,
  role: null,
  status: null,
  expires_at: null,
  created_at: null,
  workspace: null,
  organization: null,
  invited_by: null
)
```

