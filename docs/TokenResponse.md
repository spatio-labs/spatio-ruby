# Spatio::TokenResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **access_token** | **String** | Opaque bearer token. Format &#x60;tok_&lt;32 random base64url&gt;&#x60;. |  |
| **token_type** | **String** |  |  |
| **expires_in** | **Integer** | Seconds until access_token expires. |  |
| **refresh_token** | **String** |  | [optional] |
| **scope** | **String** |  | [optional] |
| **id_token** | **String** | Only present when &#x60;openid&#x60; scope was granted. RS256-signed JWT — verify against the JWKS. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::TokenResponse.new(
  access_token: null,
  token_type: Bearer,
  expires_in: null,
  refresh_token: null,
  scope: null,
  id_token: null
)
```

