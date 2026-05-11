# Spatio::ClientRegistrationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_name** | **String** |  |  |
| **redirect_uris** | **Array&lt;String&gt;** |  |  |
| **grant_types** | **Array&lt;String&gt;** |  | [optional] |
| **response_types** | **Array&lt;String&gt;** |  | [optional] |
| **scope** | **String** | Space-separated scope list. Defaults to &#x60;read:*&#x60;. | [optional] |
| **token_endpoint_auth_method** | **String** |  | [optional][default to &#39;none&#39;] |
| **client_uri** | **String** |  | [optional] |
| **logo_uri** | **String** |  | [optional] |
| **policy_uri** | **String** |  | [optional] |
| **tos_uri** | **String** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ClientRegistrationRequest.new(
  client_name: null,
  redirect_uris: null,
  grant_types: null,
  response_types: null,
  scope: null,
  token_endpoint_auth_method: null,
  client_uri: null,
  logo_uri: null,
  policy_uri: null,
  tos_uri: null
)
```

