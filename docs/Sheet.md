# Spatio::Sheet

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** | Registered provider id (e.g. &#x60;native-sheets&#x60;). | [optional] |
| **account_id** | **String** | Connected-account row this sheet belongs to. | [optional] |
| **owner_user_id** | **String** | User id of the sheet owner; non-native providers leave empty. | [optional] |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **data** | **Hash&lt;String, Object&gt;** | Free-form provider blob. Treat as opaque. | [optional] |
| **row_count** | **Integer** |  |  |
| **column_count** | **Integer** |  |  |
| **sheet_count** | **Integer** | Tab count when the file contains multiple sheets. |  |
| **is_public** | **Boolean** |  |  |
| **is_read_only** | **Boolean** |  |  |
| **file_size** | **Integer** |  | [optional] |
| **last_accessed_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Sheet.new(
  id: null,
  provider: null,
  account_id: null,
  owner_user_id: null,
  name: null,
  description: null,
  data: null,
  row_count: null,
  column_count: null,
  sheet_count: null,
  is_public: null,
  is_read_only: null,
  file_size: null,
  last_accessed_at: null,
  created_at: null,
  updated_at: null
)
```

