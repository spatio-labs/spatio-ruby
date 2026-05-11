# Spatio::Organization

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  |  |
| **slug** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **logo_url** | **String** |  | [optional] |
| **role** | **String** | The caller&#39;s role in this org (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;billing_admin&#x60;, &#x60;member&#x60;). |  |
| **member_count** | **Integer** |  | [optional] |
| **workspace_count** | **Integer** |  | [optional] |
| **workspaces** | [**Array&lt;OrganizationWorkspacesInner&gt;**](OrganizationWorkspacesInner.md) | Compact workspace summaries embedded in the org-list response. | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Organization.new(
  id: null,
  name: null,
  slug: null,
  description: null,
  logo_url: null,
  role: null,
  member_count: null,
  workspace_count: null,
  workspaces: null,
  created_at: null,
  updated_at: null
)
```

