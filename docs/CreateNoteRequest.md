# Spatio::CreateNoteRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **title** | **String** |  |  |
| **content** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **cover_image** | **String** |  | [optional] |
| **parent_id** | **String** |  | [optional] |
| **properties** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **account_id** | **String** | Optional override for the target connected account. May also be passed as a &#x60;?accountId&#x3D;&#x60; query param.  | [optional] |
| **provider** | **String** | Optional provider id (alternative to &#x60;accountId&#x60; when only one account exists for the provider). May also be passed as a &#x60;?provider&#x3D;&#x60; query param.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateNoteRequest.new(
  title: null,
  content: null,
  icon: null,
  cover_image: null,
  parent_id: null,
  properties: null,
  account_id: null,
  provider: null
)
```

