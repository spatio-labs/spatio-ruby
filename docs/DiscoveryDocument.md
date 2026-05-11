# Spatio::DiscoveryDocument

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **issuer** | **String** |  |  |
| **authorization_endpoint** | **String** |  |  |
| **token_endpoint** | **String** |  |  |
| **registration_endpoint** | **String** |  | [optional] |
| **introspection_endpoint** | **String** |  | [optional] |
| **revocation_endpoint** | **String** |  | [optional] |
| **userinfo_endpoint** | **String** |  | [optional] |
| **jwks_uri** | **String** |  |  |
| **response_types_supported** | **Array&lt;String&gt;** |  | [optional] |
| **grant_types_supported** | **Array&lt;String&gt;** |  | [optional] |
| **token_endpoint_auth_methods_supported** | **Array&lt;String&gt;** |  | [optional] |
| **code_challenge_methods_supported** | **Array&lt;String&gt;** |  | [optional] |
| **scopes_supported** | **Array&lt;String&gt;** |  |  |
| **subject_types_supported** | **Array&lt;String&gt;** |  | [optional] |
| **id_token_signing_alg_values_supported** | **Array&lt;String&gt;** |  | [optional] |
| **prompt_values_supported** | **Array&lt;String&gt;** |  | [optional] |
| **claims_supported** | **Array&lt;String&gt;** |  | [optional] |
| **service_documentation** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::DiscoveryDocument.new(
  issuer: https://api.spatio.app,
  authorization_endpoint: https://api.spatio.app/oauth2/authorize,
  token_endpoint: https://api.spatio.app/oauth2/token,
  registration_endpoint: null,
  introspection_endpoint: null,
  revocation_endpoint: null,
  userinfo_endpoint: null,
  jwks_uri: https://api.spatio.app/.well-known/jwks.json,
  response_types_supported: null,
  grant_types_supported: null,
  token_endpoint_auth_methods_supported: null,
  code_challenge_methods_supported: [&quot;S256&quot;],
  scopes_supported: null,
  subject_types_supported: [&quot;public&quot;],
  id_token_signing_alg_values_supported: [&quot;RS256&quot;],
  prompt_values_supported: [&quot;none&quot;,&quot;login&quot;,&quot;consent&quot;],
  claims_supported: null,
  service_documentation: null
)
```

