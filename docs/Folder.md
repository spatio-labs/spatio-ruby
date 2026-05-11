# Spatio::Folder

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **parent_id** | **String** |  | [optional] |
| **path** | **String** | Display path from the root (e.g. &#x60;/Finance/Q3&#x60;). |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Folder.new(
  id: null,
  provider: null,
  account_id: null,
  name: null,
  parent_id: null,
  path: null,
  created_at: null,
  updated_at: null
)
```

