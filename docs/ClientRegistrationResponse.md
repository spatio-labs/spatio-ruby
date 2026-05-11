# Spatio::ClientRegistrationResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_id** | **String** |  |  |
| **client_secret** | **String** | Only returned when token_endpoint_auth_method is client_secret_*. | [optional] |
| **client_name** | **String** |  |  |
| **redirect_uris** | **Array&lt;String&gt;** |  |  |
| **grant_types** | **Array&lt;String&gt;** |  | [optional] |
| **response_types** | **Array&lt;String&gt;** |  | [optional] |
| **scope** | **String** |  | [optional] |
| **token_endpoint_auth_method** | **String** |  | [optional] |
| **registration_access_token** | **String** |  |  |
| **registration_client_uri** | **String** |  | [optional] |
| **client_id_issued_at** | **Integer** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ClientRegistrationResponse.new(
  client_id: null,
  client_secret: null,
  client_name: null,
  redirect_uris: null,
  grant_types: null,
  response_types: null,
  scope: null,
  token_endpoint_auth_method: null,
  registration_access_token: null,
  registration_client_uri: null,
  client_id_issued_at: null
)
```

