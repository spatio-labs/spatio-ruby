# Spatio::ShareSettings

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **is_public** | **Boolean** |  |  |
| **has_password** | **Boolean** |  |  |
| **share_token** | **String** | Opaque token embedded in the public URL. Empty when &#x60;isPublic&#x60; is false.  | [optional] |
| **share_url** | **String** | Fully-qualified public viewer URL. Computed server-side from &#x60;PUBLIC_VIEWER_BASE&#x60; (defaults to &#x60;https://spatio.app&#x60;) and the share token. Empty when the note is private.  | [optional] |
| **password_set_at** | **Time** | When the current password was set, if any. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ShareSettings.new(
  is_public: null,
  has_password: null,
  share_token: null,
  share_url: null,
  password_set_at: null
)
```

