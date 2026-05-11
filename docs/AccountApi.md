# Spatio::AccountApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**change_password**](AccountApi.md#change_password) | **POST** /v1/account/security/password | Change or set the account password. |
| [**consume_agent_task**](AccountApi.md#consume_agent_task) | **POST** /v1/account/usage/consume-agent-task | Atomic check + increment on the agent-task counter (one slot per turn). |
| [**get_account_plan**](AccountApi.md#get_account_plan) | **GET** /v1/account/plan | The caller&#39;s subscription tier and status. |
| [**get_account_tier**](AccountApi.md#get_account_tier) | **GET** /v1/account/tier | Capability + quota envelope for the caller&#39;s tier. |
| [**get_account_usage**](AccountApi.md#get_account_usage) | **GET** /v1/account/usage | Today&#39;s usage counters across notes, sheets, slides, files, tasks, mail, API. |
| [**get_agent_task_usage**](AccountApi.md#get_agent_task_usage) | **GET** /v1/account/usage/agent-tasks | Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST &#x60;/v1/account/usage/consume-agent-task&#x60; atomically per turn to gate a tool-using turn.  |
| [**get_sign_in_methods**](AccountApi.md#get_sign_in_methods) | **GET** /v1/account/security/sign-in-methods | List the linked sign-in methods (password + OAuth providers). |
| [**list_connected_apps**](AccountApi.md#list_connected_apps) | **GET** /v1/account/connected-apps | List the OAuth clients the calling user has granted access to. |
| [**list_sessions**](AccountApi.md#list_sessions) | **GET** /v1/account/security/sessions | List active sessions for the caller. |
| [**revoke_connected_app**](AccountApi.md#revoke_connected_app) | **DELETE** /v1/account/connected-apps/{client_id} | Revoke a connected app and all of its active tokens. |
| [**revoke_other_sessions**](AccountApi.md#revoke_other_sessions) | **POST** /v1/account/security/sessions/revoke-others | Revoke every session except the caller&#39;s current one. |
| [**revoke_session**](AccountApi.md#revoke_session) | **DELETE** /v1/account/security/sessions/{id} | Revoke a specific session. |


## change_password

> change_password(change_password_request)

Change or set the account password.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new
change_password_request = Spatio::ChangePasswordRequest.new({new_password: 'new_password_example'}) # ChangePasswordRequest | 

begin
  # Change or set the account password.
  api_instance.change_password(change_password_request)
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->change_password: #{e}"
end
```

#### Using the change_password_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> change_password_with_http_info(change_password_request)

```ruby
begin
  # Change or set the account password.
  data, status_code, headers = api_instance.change_password_with_http_info(change_password_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->change_password_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **change_password_request** | [**ChangePasswordRequest**](ChangePasswordRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## consume_agent_task

> <ConsumeAgentTaskResponse> consume_agent_task

Atomic check + increment on the agent-task counter (one slot per turn).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # Atomic check + increment on the agent-task counter (one slot per turn).
  result = api_instance.consume_agent_task
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->consume_agent_task: #{e}"
end
```

#### Using the consume_agent_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConsumeAgentTaskResponse>, Integer, Hash)> consume_agent_task_with_http_info

```ruby
begin
  # Atomic check + increment on the agent-task counter (one slot per turn).
  data, status_code, headers = api_instance.consume_agent_task_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConsumeAgentTaskResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->consume_agent_task_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ConsumeAgentTaskResponse**](ConsumeAgentTaskResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_account_plan

> <AccountPlan> get_account_plan

The caller's subscription tier and status.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # The caller's subscription tier and status.
  result = api_instance.get_account_plan
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_plan: #{e}"
end
```

#### Using the get_account_plan_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AccountPlan>, Integer, Hash)> get_account_plan_with_http_info

```ruby
begin
  # The caller's subscription tier and status.
  data, status_code, headers = api_instance.get_account_plan_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AccountPlan>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_plan_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccountPlan**](AccountPlan.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_account_tier

> <AccountTierDetails> get_account_tier

Capability + quota envelope for the caller's tier.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # Capability + quota envelope for the caller's tier.
  result = api_instance.get_account_tier
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_tier: #{e}"
end
```

#### Using the get_account_tier_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AccountTierDetails>, Integer, Hash)> get_account_tier_with_http_info

```ruby
begin
  # Capability + quota envelope for the caller's tier.
  data, status_code, headers = api_instance.get_account_tier_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AccountTierDetails>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_tier_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccountTierDetails**](AccountTierDetails.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_account_usage

> <AccountUsage> get_account_usage

Today's usage counters across notes, sheets, slides, files, tasks, mail, API.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # Today's usage counters across notes, sheets, slides, files, tasks, mail, API.
  result = api_instance.get_account_usage
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_usage: #{e}"
end
```

#### Using the get_account_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AccountUsage>, Integer, Hash)> get_account_usage_with_http_info

```ruby
begin
  # Today's usage counters across notes, sheets, slides, files, tasks, mail, API.
  data, status_code, headers = api_instance.get_account_usage_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AccountUsage>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_account_usage_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccountUsage**](AccountUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_agent_task_usage

> <AgentTaskUsage> get_agent_task_usage

Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST `/v1/account/usage/consume-agent-task` atomically per turn to gate a tool-using turn. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST `/v1/account/usage/consume-agent-task` atomically per turn to gate a tool-using turn. 
  result = api_instance.get_agent_task_usage
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_agent_task_usage: #{e}"
end
```

#### Using the get_agent_task_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentTaskUsage>, Integer, Hash)> get_agent_task_usage_with_http_info

```ruby
begin
  # Free-trial agent-task counter snapshot. Read-only; does NOT consume a slot. Use POST `/v1/account/usage/consume-agent-task` atomically per turn to gate a tool-using turn. 
  data, status_code, headers = api_instance.get_agent_task_usage_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentTaskUsage>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_agent_task_usage_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AgentTaskUsage**](AgentTaskUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_sign_in_methods

> <SignInMethods> get_sign_in_methods

List the linked sign-in methods (password + OAuth providers).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # List the linked sign-in methods (password + OAuth providers).
  result = api_instance.get_sign_in_methods
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_sign_in_methods: #{e}"
end
```

#### Using the get_sign_in_methods_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SignInMethods>, Integer, Hash)> get_sign_in_methods_with_http_info

```ruby
begin
  # List the linked sign-in methods (password + OAuth providers).
  data, status_code, headers = api_instance.get_sign_in_methods_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SignInMethods>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->get_sign_in_methods_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SignInMethods**](SignInMethods.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_connected_apps

> <ConnectedAppsListResponse> list_connected_apps

List the OAuth clients the calling user has granted access to.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # List the OAuth clients the calling user has granted access to.
  result = api_instance.list_connected_apps
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->list_connected_apps: #{e}"
end
```

#### Using the list_connected_apps_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConnectedAppsListResponse>, Integer, Hash)> list_connected_apps_with_http_info

```ruby
begin
  # List the OAuth clients the calling user has granted access to.
  data, status_code, headers = api_instance.list_connected_apps_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConnectedAppsListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->list_connected_apps_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ConnectedAppsListResponse**](ConnectedAppsListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_sessions

> <SessionListResponse> list_sessions

List active sessions for the caller.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # List active sessions for the caller.
  result = api_instance.list_sessions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->list_sessions: #{e}"
end
```

#### Using the list_sessions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SessionListResponse>, Integer, Hash)> list_sessions_with_http_info

```ruby
begin
  # List active sessions for the caller.
  data, status_code, headers = api_instance.list_sessions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SessionListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->list_sessions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SessionListResponse**](SessionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_connected_app

> revoke_connected_app(client_id)

Revoke a connected app and all of its active tokens.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new
client_id = 'client_id_example' # String | 

begin
  # Revoke a connected app and all of its active tokens.
  api_instance.revoke_connected_app(client_id)
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_connected_app: #{e}"
end
```

#### Using the revoke_connected_app_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_connected_app_with_http_info(client_id)

```ruby
begin
  # Revoke a connected app and all of its active tokens.
  data, status_code, headers = api_instance.revoke_connected_app_with_http_info(client_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_connected_app_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## revoke_other_sessions

> <RevokeOtherSessionsResponse> revoke_other_sessions

Revoke every session except the caller's current one.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new

begin
  # Revoke every session except the caller's current one.
  result = api_instance.revoke_other_sessions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_other_sessions: #{e}"
end
```

#### Using the revoke_other_sessions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RevokeOtherSessionsResponse>, Integer, Hash)> revoke_other_sessions_with_http_info

```ruby
begin
  # Revoke every session except the caller's current one.
  data, status_code, headers = api_instance.revoke_other_sessions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RevokeOtherSessionsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_other_sessions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**RevokeOtherSessionsResponse**](RevokeOtherSessionsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_session

> revoke_session(id)

Revoke a specific session.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AccountApi.new
id = 'id_example' # String | 

begin
  # Revoke a specific session.
  api_instance.revoke_session(id)
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_session: #{e}"
end
```

#### Using the revoke_session_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_session_with_http_info(id)

```ruby
begin
  # Revoke a specific session.
  data, status_code, headers = api_instance.revoke_session_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AccountApi->revoke_session_with_http_info: #{e}"
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

