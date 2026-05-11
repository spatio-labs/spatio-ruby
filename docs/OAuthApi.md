# Spatio::OAuthApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_jwks**](OAuthApi.md#get_jwks) | **GET** /.well-known/jwks.json | JSON Web Key Set for id_token verification (RFC 7517). |
| [**get_o_auth_discovery**](OAuthApi.md#get_o_auth_discovery) | **GET** /.well-known/oauth-authorization-server | OAuth 2.1 authorization server metadata (RFC 8414). |
| [**get_open_id_configuration**](OAuthApi.md#get_open_id_configuration) | **GET** /.well-known/openid-configuration | OpenID Connect Discovery 1.0 metadata. |
| [**get_user_info**](OAuthApi.md#get_user_info) | **GET** /oauth2/userinfo | OIDC UserInfo (OpenID Connect Core 1.0 §5.3). |
| [**oauth_authorize**](OAuthApi.md#oauth_authorize) | **GET** /oauth2/authorize | OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE). |
| [**oauth_introspect**](OAuthApi.md#oauth_introspect) | **POST** /oauth2/introspect | RFC 7662 token introspection. Accepts both OAuth access tokens and PATs. |
| [**oauth_revoke**](OAuthApi.md#oauth_revoke) | **POST** /oauth2/revoke | RFC 7009 token revocation. Idempotent. |
| [**oauth_token**](OAuthApi.md#oauth_token) | **POST** /oauth2/token | Exchange authorization code or refresh token for an access token (+ id_token if &#x60;openid&#x60; scope). |
| [**post_user_info**](OAuthApi.md#post_user_info) | **POST** /oauth2/userinfo | Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body. |
| [**register_o_auth_client**](OAuthApi.md#register_o_auth_client) | **POST** /oauth2/register | Register a new OAuth 2.1 client (RFC 7591 dynamic client registration). |


## get_jwks

> <JWKS> get_jwks

JSON Web Key Set for id_token verification (RFC 7517).

The set of public keys RPs use to verify Spatio-issued id_tokens. Cached for 5 minutes at the edge. Always includes the currently-active signing key plus any retired keys that may still be in circulation (id_token TTL is 1 hour + slack). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new

begin
  # JSON Web Key Set for id_token verification (RFC 7517).
  result = api_instance.get_jwks
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_jwks: #{e}"
end
```

#### Using the get_jwks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<JWKS>, Integer, Hash)> get_jwks_with_http_info

```ruby
begin
  # JSON Web Key Set for id_token verification (RFC 7517).
  data, status_code, headers = api_instance.get_jwks_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <JWKS>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_jwks_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**JWKS**](JWKS.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_o_auth_discovery

> <DiscoveryDocument> get_o_auth_discovery

OAuth 2.1 authorization server metadata (RFC 8414).

Returns the canonical metadata for the Spatio OAuth 2.1 + OpenID Connect server. Third-party RPs use this to auto-discover endpoint URLs, supported scopes, and signing algorithms.  Identical payload to `/.well-known/openid-configuration` — either path is acceptable; OIDC clients prefer the openid-configuration alias. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new

begin
  # OAuth 2.1 authorization server metadata (RFC 8414).
  result = api_instance.get_o_auth_discovery
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_o_auth_discovery: #{e}"
end
```

#### Using the get_o_auth_discovery_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoveryDocument>, Integer, Hash)> get_o_auth_discovery_with_http_info

```ruby
begin
  # OAuth 2.1 authorization server metadata (RFC 8414).
  data, status_code, headers = api_instance.get_o_auth_discovery_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoveryDocument>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_o_auth_discovery_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**DiscoveryDocument**](DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_open_id_configuration

> <DiscoveryDocument> get_open_id_configuration

OpenID Connect Discovery 1.0 metadata.

Alias of `/.well-known/oauth-authorization-server`. Provided so OIDC client libraries (NextAuth, Auth.js, oidc-client-ts, passport-openidconnect) auto-detect Spatio as an OIDC provider via their `wellKnown` / `discoveryUrl` config field. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new

begin
  # OpenID Connect Discovery 1.0 metadata.
  result = api_instance.get_open_id_configuration
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_open_id_configuration: #{e}"
end
```

#### Using the get_open_id_configuration_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DiscoveryDocument>, Integer, Hash)> get_open_id_configuration_with_http_info

```ruby
begin
  # OpenID Connect Discovery 1.0 metadata.
  data, status_code, headers = api_instance.get_open_id_configuration_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DiscoveryDocument>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_open_id_configuration_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**DiscoveryDocument**](DiscoveryDocument.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_user_info

> <UserInfoResponse> get_user_info

OIDC UserInfo (OpenID Connect Core 1.0 §5.3).

Returns user claims gated by the scopes on the presenting access token. `sub` is always returned; `email`, `name`, etc. require their respective scopes. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OAuthApi.new

begin
  # OIDC UserInfo (OpenID Connect Core 1.0 §5.3).
  result = api_instance.get_user_info
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_user_info: #{e}"
end
```

#### Using the get_user_info_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UserInfoResponse>, Integer, Hash)> get_user_info_with_http_info

```ruby
begin
  # OIDC UserInfo (OpenID Connect Core 1.0 §5.3).
  data, status_code, headers = api_instance.get_user_info_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UserInfoResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->get_user_info_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**UserInfoResponse**](UserInfoResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## oauth_authorize

> oauth_authorize(client_id, redirect_uri, response_type, code_challenge, code_challenge_method, opts)

OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE).

Browser-redirect endpoint. Validates the client + redirect_uri, packs the request into a signed JWT, and 302s the user's browser to the consent UI. The consent UI then POSTs to `/oauth2/authorize/confirm` with the user's decision.  OIDC additions: `scope=openid+profile+email`, `nonce`, `prompt` (none|login|consent), `max_age`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new
client_id = 'client_id_example' # String | 
redirect_uri = 'redirect_uri_example' # String | 
response_type = 'code' # String | 
code_challenge = 'code_challenge_example' # String | 
code_challenge_method = 'S256' # String | 
opts = {
  scope: 'scope_example', # String | 
  state: 'state_example', # String | 
  nonce: 'nonce_example', # String | 
  prompt: 'none', # String | 
  max_age: 56 # Integer | 
}

begin
  # OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE).
  api_instance.oauth_authorize(client_id, redirect_uri, response_type, code_challenge, code_challenge_method, opts)
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_authorize: #{e}"
end
```

#### Using the oauth_authorize_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> oauth_authorize_with_http_info(client_id, redirect_uri, response_type, code_challenge, code_challenge_method, opts)

```ruby
begin
  # OAuth 2.1 authorization endpoint (RFC 6749 + 7636 PKCE).
  data, status_code, headers = api_instance.oauth_authorize_with_http_info(client_id, redirect_uri, response_type, code_challenge, code_challenge_method, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_authorize_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_id** | **String** |  |  |
| **redirect_uri** | **String** |  |  |
| **response_type** | **String** |  |  |
| **code_challenge** | **String** |  |  |
| **code_challenge_method** | **String** |  |  |
| **scope** | **String** |  | [optional] |
| **state** | **String** |  | [optional] |
| **nonce** | **String** |  | [optional] |
| **prompt** | **String** |  | [optional] |
| **max_age** | **Integer** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## oauth_introspect

> <IntrospectionResponse> oauth_introspect(token)

RFC 7662 token introspection. Accepts both OAuth access tokens and PATs.

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new
token = 'token_example' # String | 

begin
  # RFC 7662 token introspection. Accepts both OAuth access tokens and PATs.
  result = api_instance.oauth_introspect(token)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_introspect: #{e}"
end
```

#### Using the oauth_introspect_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IntrospectionResponse>, Integer, Hash)> oauth_introspect_with_http_info(token)

```ruby
begin
  # RFC 7662 token introspection. Accepts both OAuth access tokens and PATs.
  data, status_code, headers = api_instance.oauth_introspect_with_http_info(token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IntrospectionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_introspect_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |

### Return type

[**IntrospectionResponse**](IntrospectionResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: application/json


## oauth_revoke

> oauth_revoke(token)

RFC 7009 token revocation. Idempotent.

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new
token = 'token_example' # String | 

begin
  # RFC 7009 token revocation. Idempotent.
  api_instance.oauth_revoke(token)
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_revoke: #{e}"
end
```

#### Using the oauth_revoke_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> oauth_revoke_with_http_info(token)

```ruby
begin
  # RFC 7009 token revocation. Idempotent.
  data, status_code, headers = api_instance.oauth_revoke_with_http_info(token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_revoke_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: Not defined


## oauth_token

> <TokenResponse> oauth_token(grant_type, opts)

Exchange authorization code or refresh token for an access token (+ id_token if `openid` scope).

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new
grant_type = 'authorization_code' # String | 
opts = {
  code: 'code_example', # String | Required for authorization_code grant.
  code_verifier: 'code_verifier_example', # String | PKCE verifier — required for authorization_code grant.
  redirect_uri: 'redirect_uri_example', # String | 
  refresh_token: 'refresh_token_example', # String | Required for refresh_token grant.
  client_id: 'client_id_example', # String | 
  client_secret: 'client_secret_example' # String | 
}

begin
  # Exchange authorization code or refresh token for an access token (+ id_token if `openid` scope).
  result = api_instance.oauth_token(grant_type, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_token: #{e}"
end
```

#### Using the oauth_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TokenResponse>, Integer, Hash)> oauth_token_with_http_info(grant_type, opts)

```ruby
begin
  # Exchange authorization code or refresh token for an access token (+ id_token if `openid` scope).
  data, status_code, headers = api_instance.oauth_token_with_http_info(grant_type, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TokenResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->oauth_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **grant_type** | **String** |  |  |
| **code** | **String** | Required for authorization_code grant. | [optional] |
| **code_verifier** | **String** | PKCE verifier — required for authorization_code grant. | [optional] |
| **redirect_uri** | **String** |  | [optional] |
| **refresh_token** | **String** | Required for refresh_token grant. | [optional] |
| **client_id** | **String** |  | [optional] |
| **client_secret** | **String** |  | [optional] |

### Return type

[**TokenResponse**](TokenResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: application/json


## post_user_info

> <UserInfoResponse> post_user_info

Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OAuthApi.new

begin
  # Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body.
  result = api_instance.post_user_info
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->post_user_info: #{e}"
end
```

#### Using the post_user_info_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UserInfoResponse>, Integer, Hash)> post_user_info_with_http_info

```ruby
begin
  # Same as GET /oauth2/userinfo. Provided for clients that send the bearer in the body.
  data, status_code, headers = api_instance.post_user_info_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UserInfoResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->post_user_info_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**UserInfoResponse**](UserInfoResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## register_o_auth_client

> <ClientRegistrationResponse> register_o_auth_client(client_registration_request)

Register a new OAuth 2.1 client (RFC 7591 dynamic client registration).

Returns a fresh `client_id` (and, for confidential clients, `client_secret`) plus a one-time `registration_access_token` the client can use later to update its registration. Public clients (mobile, SPA) MUST use `token_endpoint_auth_method: none` and PKCE.  Rate-limited to 10 registrations per hour per source IP. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::OAuthApi.new
client_registration_request = Spatio::ClientRegistrationRequest.new({client_name: 'client_name_example', redirect_uris: ['redirect_uris_example']}) # ClientRegistrationRequest | 

begin
  # Register a new OAuth 2.1 client (RFC 7591 dynamic client registration).
  result = api_instance.register_o_auth_client(client_registration_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->register_o_auth_client: #{e}"
end
```

#### Using the register_o_auth_client_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ClientRegistrationResponse>, Integer, Hash)> register_o_auth_client_with_http_info(client_registration_request)

```ruby
begin
  # Register a new OAuth 2.1 client (RFC 7591 dynamic client registration).
  data, status_code, headers = api_instance.register_o_auth_client_with_http_info(client_registration_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ClientRegistrationResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OAuthApi->register_o_auth_client_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_registration_request** | [**ClientRegistrationRequest**](ClientRegistrationRequest.md) |  |  |

### Return type

[**ClientRegistrationResponse**](ClientRegistrationResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

