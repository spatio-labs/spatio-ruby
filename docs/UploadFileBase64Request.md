# Spatio::UploadFileBase64Request

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **content** | **String** | Base64-encoded file bytes. |  |
| **mime_type** | **String** |  |  |
| **folder_id** | **String** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UploadFileBase64Request.new(
  account_id: null,
  name: null,
  content: null,
  mime_type: null,
  folder_id: null,
  workspace_id: null,
  organization_id: null,
  metadata: null
)
```

