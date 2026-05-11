# Spatio::JWK

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **kty** | **String** |  |  |
| **use** | **String** |  |  |
| **alg** | **String** |  |  |
| **kid** | **String** |  |  |
| **n** | **String** | Base64url-encoded RSA modulus. |  |
| **e** | **String** | Base64url-encoded RSA exponent. Almost always \&quot;AQAB\&quot;. |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::JWK.new(
  kty: RSA,
  use: sig,
  alg: RS256,
  kid: null,
  n: null,
  e: null
)
```

