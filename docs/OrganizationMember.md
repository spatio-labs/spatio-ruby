# Spatio::OrganizationMember

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | &#x60;OrganizationMember&#x60; row id. |  |
| **user_id** | **String** |  |  |
| **role** | **String** |  |  |
| **joined_at** | **Time** |  |  |
| **invited_by** | [**OrganizationMemberInvitedBy**](OrganizationMemberInvitedBy.md) |  | [optional] |
| **user** | **Hash&lt;String, Object&gt;** | Embedded user-profile fields (id, email, name, profilePhoto, ...). | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::OrganizationMember.new(
  id: null,
  user_id: null,
  role: null,
  joined_at: null,
  invited_by: null,
  user: null
)
```

