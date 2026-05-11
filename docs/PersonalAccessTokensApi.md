# Spatio::PersonalAccessTokensApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_personal_access_token**](PersonalAccessTokensApi.md#create_personal_access_token) | **POST** /v1/tokens | Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again.  |
| [**list_available_pat_scopes**](PersonalAccessTokensApi.md#list_available_pat_scopes) | **GET** /v1/tokens/scopes | List the scope strings PATs can be issued with. |
| [**list_personal_access_tokens**](PersonalAccessTokensApi.md#list_personal_access_tokens) | **GET** /v1/tokens | List the caller&#39;s personal access tokens (with available scopes). |
| [**revoke_personal_access_token**](PersonalAccessTokensApi.md#revoke_personal_access_token) | **DELETE** /v1/tokens/{id} | Revoke a PAT. |
| [**update_personal_access_token**](PersonalAccessTokensApi.md#update_personal_access_token) | **PATCH** /v1/tokens/{id} | Rename or re-describe a PAT (scopes are immutable). |
| [**workspace_create_pat**](PersonalAccessTokensApi.md#workspace_create_pat) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspace_list_pats**](PersonalAccessTokensApi.md#workspace_list_pats) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tokens |  |
| [**workspace_revoke_pat**](PersonalAccessTokensApi.md#workspace_revoke_pat) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |
| [**workspace_update_pat**](PersonalAccessTokensApi.md#workspace_update_pat) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tokens/{id} |  |


## create_personal_access_token

> <CreatePATResponse> create_personal_access_token(create_pat_request)

Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
create_pat_request = Spatio::CreatePATRequest.new({name: 'name_example'}) # CreatePATRequest | 

begin
  # Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again. 
  result = api_instance.create_personal_access_token(create_pat_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->create_personal_access_token: #{e}"
end
```

#### Using the create_personal_access_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreatePATResponse>, Integer, Hash)> create_personal_access_token_with_http_info(create_pat_request)

```ruby
begin
  # Create a new PAT. The full token is returned only once on creation; the API never reveals the secret again. 
  data, status_code, headers = api_instance.create_personal_access_token_with_http_info(create_pat_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreatePATResponse>
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->create_personal_access_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_pat_request** | [**CreatePATRequest**](CreatePATRequest.md) |  |  |

### Return type

[**CreatePATResponse**](CreatePATResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_available_pat_scopes

> <PATScopesResponse> list_available_pat_scopes

List the scope strings PATs can be issued with.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new

begin
  # List the scope strings PATs can be issued with.
  result = api_instance.list_available_pat_scopes
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->list_available_pat_scopes: #{e}"
end
```

#### Using the list_available_pat_scopes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PATScopesResponse>, Integer, Hash)> list_available_pat_scopes_with_http_info

```ruby
begin
  # List the scope strings PATs can be issued with.
  data, status_code, headers = api_instance.list_available_pat_scopes_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PATScopesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->list_available_pat_scopes_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**PATScopesResponse**](PATScopesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_personal_access_tokens

> <PATListResponse> list_personal_access_tokens

List the caller's personal access tokens (with available scopes).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new

begin
  # List the caller's personal access tokens (with available scopes).
  result = api_instance.list_personal_access_tokens
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->list_personal_access_tokens: #{e}"
end
```

#### Using the list_personal_access_tokens_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PATListResponse>, Integer, Hash)> list_personal_access_tokens_with_http_info

```ruby
begin
  # List the caller's personal access tokens (with available scopes).
  data, status_code, headers = api_instance.list_personal_access_tokens_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PATListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->list_personal_access_tokens_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**PATListResponse**](PATListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_personal_access_token

> revoke_personal_access_token(id)

Revoke a PAT.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
id = 'id_example' # String | 

begin
  # Revoke a PAT.
  api_instance.revoke_personal_access_token(id)
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->revoke_personal_access_token: #{e}"
end
```

#### Using the revoke_personal_access_token_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_personal_access_token_with_http_info(id)

```ruby
begin
  # Revoke a PAT.
  data, status_code, headers = api_instance.revoke_personal_access_token_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->revoke_personal_access_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_personal_access_token

> <PersonalAccessToken> update_personal_access_token(id, update_pat_request)

Rename or re-describe a PAT (scopes are immutable).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
id = 'id_example' # String | 
update_pat_request = Spatio::UpdatePATRequest.new # UpdatePATRequest | 

begin
  # Rename or re-describe a PAT (scopes are immutable).
  result = api_instance.update_personal_access_token(id, update_pat_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->update_personal_access_token: #{e}"
end
```

#### Using the update_personal_access_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PersonalAccessToken>, Integer, Hash)> update_personal_access_token_with_http_info(id, update_pat_request)

```ruby
begin
  # Rename or re-describe a PAT (scopes are immutable).
  data, status_code, headers = api_instance.update_personal_access_token_with_http_info(id, update_pat_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PersonalAccessToken>
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->update_personal_access_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_pat_request** | [**UpdatePATRequest**](UpdatePATRequest.md) |  |  |

### Return type

[**PersonalAccessToken**](PersonalAccessToken.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_pat

> Hash&lt;String, Object&gt; workspace_create_pat(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_pat(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_create_pat: #{e}"
end
```

#### Using the workspace_create_pat_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_pat_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_pat_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_create_pat_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_list_pats

> Hash&lt;String, Object&gt; workspace_list_pats(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_pats(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_list_pats: #{e}"
end
```

#### Using the workspace_list_pats_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_pats_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_pats_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_list_pats_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_revoke_pat

> workspace_revoke_pat(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_revoke_pat(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_revoke_pat: #{e}"
end
```

#### Using the workspace_revoke_pat_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_revoke_pat_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_revoke_pat_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_revoke_pat_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_update_pat

> Hash&lt;String, Object&gt; workspace_update_pat(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PersonalAccessTokensApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_pat(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_update_pat: #{e}"
end
```

#### Using the workspace_update_pat_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_pat_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_pat_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PersonalAccessTokensApi->workspace_update_pat_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

