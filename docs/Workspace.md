# Spatio::Workspace

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  |  |
| **slug** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **logo_url** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **organization** | [**WorkspaceOrganization**](WorkspaceOrganization.md) |  | [optional] |
| **role** | **String** | The caller&#39;s role in this workspace (&#x60;owner&#x60;, &#x60;admin&#x60;, &#x60;member&#x60;, &#x60;guest&#x60;). | [optional] |
| **settings** | **Object** | Per-workspace settings. Currently emitted as either an object (&#x60;{language, timezone, ...}&#x60;) on &#x60;GET /v1/workspaces/{id}&#x60; or a JSON-encoded string on &#x60;GET /v1/organizations/{id}/workspaces&#x60;. Treat as opaque and parse defensively.  | [optional] |
| **is_default** | **Boolean** |  | [optional] |
| **member_count** | **Integer** |  | [optional] |
| **billing_tier** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Workspace.new(
  id: null,
  name: null,
  slug: null,
  description: null,
  logo_url: null,
  organization_id: null,
  organization: null,
  role: null,
  settings: null,
  is_default: null,
  member_count: null,
  billing_tier: null,
  created_at: null,
  updated_at: null
)
```

