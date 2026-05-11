# Spatio::Presentation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **owner_user_id** | **String** |  | [optional] |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **theme** | **String** | Free-form theme id; provider-specific. | [optional] |
| **thumbnail_url** | **String** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **last_viewed_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Presentation.new(
  id: null,
  provider: null,
  account_id: null,
  owner_user_id: null,
  title: null,
  description: null,
  theme: null,
  thumbnail_url: null,
  created_at: null,
  updated_at: null,
  last_viewed_at: null
)
```

