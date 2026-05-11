# Spatio::OrganizationDetailLegacy

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  |  |
| **slug** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **logo_url** | **String** |  | [optional] |
| **settings** | **String** | JSON-encoded settings string. Parse client-side. | [optional] |
| **subscription_tier** | **String** |  |  |
| **deployment_type** | **String** |  |  |
| **subscription_status** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::OrganizationDetailLegacy.new(
  id: null,
  name: null,
  slug: null,
  description: null,
  logo_url: null,
  settings: null,
  subscription_tier: null,
  deployment_type: null,
  subscription_status: null,
  created_at: null,
  updated_at: null
)
```

