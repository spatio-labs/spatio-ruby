# Spatio::FederatedSearchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query** | **String** |  |  |
| **platforms** | **Array&lt;String&gt;** | Subset to fan out to. Empty means all available platforms. | [optional] |
| **limit** | **Integer** |  | [optional][default to 25] |
| **page_tokens** | **Hash&lt;String, String&gt;** | Per-platform cursor for pagination. | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **include_shared** | **Boolean** |  | [optional] |
| **include_archived** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::FederatedSearchRequest.new(
  query: null,
  platforms: null,
  limit: null,
  page_tokens: null,
  workspace_id: null,
  organization_id: null,
  include_shared: null,
  include_archived: null
)
```

