# Spatio::FilesAndFoldersResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **files** | [**Array&lt;SpatioFile&gt;**](SpatioFile.md) |  | [optional] |
| **folders** | [**Array&lt;Folder&gt;**](Folder.md) |  | [optional] |
| **accounts** | [**Array&lt;AccountStatus&gt;**](AccountStatus.md) |  | [optional] |
| **total** | **Integer** |  |  |
| **has_more** | **Boolean** |  |  |
| **next_offset** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::FilesAndFoldersResponse.new(
  files: null,
  folders: null,
  accounts: null,
  total: null,
  has_more: null,
  next_offset: null
)
```

