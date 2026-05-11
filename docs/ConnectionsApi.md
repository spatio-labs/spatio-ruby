# Spatio::ConnectionsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**disconnect_connection**](ConnectionsApi.md#disconnect_connection) | **POST** /v1/connections/disconnect | Disconnect a connected account. |
| [**install_connection**](ConnectionsApi.md#install_connection) | **POST** /v1/connections/install | Begin an OAuth install for a connection. |
| [**list_accounts**](ConnectionsApi.md#list_accounts) | **GET** /v1/accounts | List the caller&#39;s multi-provider accounts. |
| [**list_connection_integrations**](ConnectionsApi.md#list_connection_integrations) | **GET** /v1/connections/integrations | List supported integrations + their connection state. Legacy path; &#x60;/v1/connections/list&#x60; is the preferred alias.  |
| [**list_connections**](ConnectionsApi.md#list_connections) | **GET** /v1/connections/list | List supported integrations + their connection state. |
| [**list_user_connections**](ConnectionsApi.md#list_user_connections) | **GET** /v1/connections/user | List the caller&#39;s connected accounts. |
| [**refresh_connection**](ConnectionsApi.md#refresh_connection) | **POST** /v1/connections/refresh | Force a refresh of a connection&#39;s OAuth tokens. |
| [**remove_account**](ConnectionsApi.md#remove_account) | **DELETE** /v1/accounts/{accountId} | Remove an account. |
| [**resolve_account**](ConnectionsApi.md#resolve_account) | **GET** /v1/accounts/resolve | Resolve an account by provider/identifier. |
| [**sync_account**](ConnectionsApi.md#sync_account) | **POST** /v1/accounts/{accountId}/sync | Force a sync against the upstream provider. |
| [**update_account**](ConnectionsApi.md#update_account) | **PATCH** /v1/accounts/{accountId} | Update account metadata (label, etc.). |


## disconnect_connection

> Hash&lt;String, Object&gt; disconnect_connection(disconnect_connection_request)

Disconnect a connected account.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
disconnect_connection_request = Spatio::DisconnectConnectionRequest.new({connection_id: 'connection_id_example'}) # DisconnectConnectionRequest | 

begin
  # Disconnect a connected account.
  result = api_instance.disconnect_connection(disconnect_connection_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->disconnect_connection: #{e}"
end
```

#### Using the disconnect_connection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> disconnect_connection_with_http_info(disconnect_connection_request)

```ruby
begin
  # Disconnect a connected account.
  data, status_code, headers = api_instance.disconnect_connection_with_http_info(disconnect_connection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->disconnect_connection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **disconnect_connection_request** | [**DisconnectConnectionRequest**](DisconnectConnectionRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## install_connection

> Hash&lt;String, Object&gt; install_connection(install_connection_request)

Begin an OAuth install for a connection.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
install_connection_request = Spatio::InstallConnectionRequest.new({connection_id: 'connection_id_example'}) # InstallConnectionRequest | 

begin
  # Begin an OAuth install for a connection.
  result = api_instance.install_connection(install_connection_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->install_connection: #{e}"
end
```

#### Using the install_connection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> install_connection_with_http_info(install_connection_request)

```ruby
begin
  # Begin an OAuth install for a connection.
  data, status_code, headers = api_instance.install_connection_with_http_info(install_connection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->install_connection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **install_connection_request** | [**InstallConnectionRequest**](InstallConnectionRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_accounts

> <AccountListResponse> list_accounts

List the caller's multi-provider accounts.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new

begin
  # List the caller's multi-provider accounts.
  result = api_instance.list_accounts
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_accounts: #{e}"
end
```

#### Using the list_accounts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AccountListResponse>, Integer, Hash)> list_accounts_with_http_info

```ruby
begin
  # List the caller's multi-provider accounts.
  data, status_code, headers = api_instance.list_accounts_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AccountListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_accounts_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccountListResponse**](AccountListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_connection_integrations

> <ConnectionListResponse> list_connection_integrations

List supported integrations + their connection state. Legacy path; `/v1/connections/list` is the preferred alias. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new

begin
  # List supported integrations + their connection state. Legacy path; `/v1/connections/list` is the preferred alias. 
  result = api_instance.list_connection_integrations
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_connection_integrations: #{e}"
end
```

#### Using the list_connection_integrations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConnectionListResponse>, Integer, Hash)> list_connection_integrations_with_http_info

```ruby
begin
  # List supported integrations + their connection state. Legacy path; `/v1/connections/list` is the preferred alias. 
  data, status_code, headers = api_instance.list_connection_integrations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConnectionListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_connection_integrations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ConnectionListResponse**](ConnectionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_connections

> <ConnectionListResponse> list_connections

List supported integrations + their connection state.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new

begin
  # List supported integrations + their connection state.
  result = api_instance.list_connections
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_connections: #{e}"
end
```

#### Using the list_connections_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConnectionListResponse>, Integer, Hash)> list_connections_with_http_info

```ruby
begin
  # List supported integrations + their connection state.
  data, status_code, headers = api_instance.list_connections_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConnectionListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_connections_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ConnectionListResponse**](ConnectionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_user_connections

> <ConnectionAccountListResponse> list_user_connections

List the caller's connected accounts.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new

begin
  # List the caller's connected accounts.
  result = api_instance.list_user_connections
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_user_connections: #{e}"
end
```

#### Using the list_user_connections_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConnectionAccountListResponse>, Integer, Hash)> list_user_connections_with_http_info

```ruby
begin
  # List the caller's connected accounts.
  data, status_code, headers = api_instance.list_user_connections_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConnectionAccountListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->list_user_connections_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ConnectionAccountListResponse**](ConnectionAccountListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## refresh_connection

> Hash&lt;String, Object&gt; refresh_connection(refresh_connection_request)

Force a refresh of a connection's OAuth tokens.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
refresh_connection_request = Spatio::RefreshConnectionRequest.new({connection_id: 'connection_id_example'}) # RefreshConnectionRequest | 

begin
  # Force a refresh of a connection's OAuth tokens.
  result = api_instance.refresh_connection(refresh_connection_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->refresh_connection: #{e}"
end
```

#### Using the refresh_connection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> refresh_connection_with_http_info(refresh_connection_request)

```ruby
begin
  # Force a refresh of a connection's OAuth tokens.
  data, status_code, headers = api_instance.refresh_connection_with_http_info(refresh_connection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->refresh_connection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **refresh_connection_request** | [**RefreshConnectionRequest**](RefreshConnectionRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_account

> remove_account(account_id)

Remove an account.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
account_id = 'account_id_example' # String | 

begin
  # Remove an account.
  api_instance.remove_account(account_id)
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->remove_account: #{e}"
end
```

#### Using the remove_account_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_account_with_http_info(account_id)

```ruby
begin
  # Remove an account.
  data, status_code, headers = api_instance.remove_account_with_http_info(account_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->remove_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## resolve_account

> Hash&lt;String, Object&gt; resolve_account(opts)

Resolve an account by provider/identifier.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
opts = {
  provider: 'provider_example', # String | 
  email: 'email_example' # String | 
}

begin
  # Resolve an account by provider/identifier.
  result = api_instance.resolve_account(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->resolve_account: #{e}"
end
```

#### Using the resolve_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> resolve_account_with_http_info(opts)

```ruby
begin
  # Resolve an account by provider/identifier.
  data, status_code, headers = api_instance.resolve_account_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->resolve_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## sync_account

> Hash&lt;String, Object&gt; sync_account(account_id)

Force a sync against the upstream provider.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
account_id = 'account_id_example' # String | 

begin
  # Force a sync against the upstream provider.
  result = api_instance.sync_account(account_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->sync_account: #{e}"
end
```

#### Using the sync_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> sync_account_with_http_info(account_id)

```ruby
begin
  # Force a sync against the upstream provider.
  data, status_code, headers = api_instance.sync_account_with_http_info(account_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->sync_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_account

> Hash&lt;String, Object&gt; update_account(account_id, update_account_request)

Update account metadata (label, etc.).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConnectionsApi.new
account_id = 'account_id_example' # String | 
update_account_request = Spatio::UpdateAccountRequest.new # UpdateAccountRequest | 

begin
  # Update account metadata (label, etc.).
  result = api_instance.update_account(account_id, update_account_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->update_account: #{e}"
end
```

#### Using the update_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_account_with_http_info(account_id, update_account_request)

```ruby
begin
  # Update account metadata (label, etc.).
  data, status_code, headers = api_instance.update_account_with_http_info(account_id, update_account_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ConnectionsApi->update_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  |  |
| **update_account_request** | [**UpdateAccountRequest**](UpdateAccountRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

