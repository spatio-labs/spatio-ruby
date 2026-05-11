# Spatio::OrganizationInvitation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **organization_id** | **String** |  | [optional] |
| **email** | **String** |  |  |
| **role** | **String** |  |  |
| **token** | **String** | Opaque invitation token (omitted on list responses). | [optional] |
| **expires_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **accepted_at** | **Time** |  | [optional] |
| **revoked_at** | **Time** |  | [optional] |
| **invited_by** | [**OrganizationMemberInvitedBy**](OrganizationMemberInvitedBy.md) |  | [optional] |
| **status** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::OrganizationInvitation.new(
  id: null,
  organization_id: null,
  email: null,
  role: null,
  token: null,
  expires_at: null,
  created_at: null,
  accepted_at: null,
  revoked_at: null,
  invited_by: null,
  status: null
)
```

