# Spatio::CreateOrganizationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **slug** | **String** | Auto-generated from &#x60;name&#x60; if omitted. Slug collisions are auto-suffixed with &#x60;-2&#x60;, &#x60;-3&#x60;, etc.  | [optional] |
| **description** | **String** |  | [optional] |
| **logo_url** | **String** |  | [optional] |
| **create_default_workspace** | **Boolean** | &#x60;true&#x60; (default) creates a default workspace alongside the org. | [optional] |
| **default_workspace_name** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateOrganizationRequest.new(
  name: null,
  slug: null,
  description: null,
  logo_url: null,
  create_default_workspace: null,
  default_workspace_name: null
)
```

