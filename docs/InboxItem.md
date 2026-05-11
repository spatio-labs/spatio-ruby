# Spatio::InboxItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **category** | **String** |  |  |
| **title** | **String** |  | [optional] |
| **snippet** | **String** |  | [optional] |
| **source** | **String** |  | [optional] |
| **source_id** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **is_read** | **Boolean** |  | [optional] |
| **is_mention** | **Boolean** |  | [optional] |
| **timestamp** | **Time** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::InboxItem.new(
  id: null,
  category: null,
  title: null,
  snippet: null,
  source: null,
  source_id: null,
  account_id: null,
  is_read: null,
  is_mention: null,
  timestamp: null,
  metadata: null
)
```

