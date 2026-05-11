# Spatio::MiscApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_pinned_platform**](MiscApi.md#delete_pinned_platform) | **DELETE** /v1/pinned-platforms/{platformId} | Unpin a platform. |
| [**get_bootstrap**](MiscApi.md#get_bootstrap) | **GET** /v1/bootstrap | Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx.  |
| [**get_onboarding_invitations**](MiscApi.md#get_onboarding_invitations) | **GET** /v1/onboarding/invitations | Pending invitations the caller can accept during onboarding. |
| [**get_pinned_platforms**](MiscApi.md#get_pinned_platforms) | **GET** /v1/pinned-platforms | Read the caller&#39;s pinned-platform list (sidebar order). |
| [**get_platform_preferences**](MiscApi.md#get_platform_preferences) | **GET** /v1/platform-preferences | Read the caller&#39;s per-platform sidebar/visibility preferences. |
| [**get_platform_settings_legacy**](MiscApi.md#get_platform_settings_legacy) | **GET** /v1/settings/platform | Legacy admin-tier platform settings read endpoint. |
| [**get_threads_status**](MiscApi.md#get_threads_status) | **GET** /v1/threads/status | Async-thread / job-runner status snapshot. |
| [**get_user_permissions**](MiscApi.md#get_user_permissions) | **GET** /v1/user/permissions | Read the caller&#39;s effective per-resource permissions. |
| [**get_workspace_activity**](MiscApi.md#get_workspace_activity) | **GET** /v1/workspace-activity | Recent activity feed for a workspace. |
| [**get_workspace_layout**](MiscApi.md#get_workspace_layout) | **GET** /v1/layout/{workspaceId} | Read the renderer&#39;s saved pane layout for a workspace. |
| [**put_pinned_platform**](MiscApi.md#put_pinned_platform) | **PUT** /v1/pinned-platforms | Pin a platform. |
| [**put_platform_preferences**](MiscApi.md#put_platform_preferences) | **PUT** /v1/platform-preferences | Replace the caller&#39;s platform preferences. |
| [**put_workspace_layout**](MiscApi.md#put_workspace_layout) | **PUT** /v1/layout/{workspaceId} | Save the renderer&#39;s pane layout. |
| [**reorder_pinned_platforms**](MiscApi.md#reorder_pinned_platforms) | **POST** /v1/pinned-platforms/reorder | Reorder the pinned-platform list. |
| [**reset_platform_preferences**](MiscApi.md#reset_platform_preferences) | **POST** /v1/platform-preferences/reset | Reset platform preferences to defaults. |
| [**update_user_profile**](MiscApi.md#update_user_profile) | **PATCH** /v1/user/profile | Update the caller&#39;s user profile (name, avatar, etc.). |
| [**validate_organization_slug**](MiscApi.md#validate_organization_slug) | **GET** /v1/validate-slug/organization | Check whether an org slug is available. |
| [**validate_workspace_slug**](MiscApi.md#validate_workspace_slug) | **GET** /v1/validate-slug/workspace | Check whether a workspace slug is available. |


## delete_pinned_platform

> delete_pinned_platform(platform_id)

Unpin a platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Unpin a platform.
  api_instance.delete_pinned_platform(platform_id)
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->delete_pinned_platform: #{e}"
end
```

#### Using the delete_pinned_platform_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_pinned_platform_with_http_info(platform_id)

```ruby
begin
  # Unpin a platform.
  data, status_code, headers = api_instance.delete_pinned_platform_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->delete_pinned_platform_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_bootstrap

> Hash&lt;String, Object&gt; get_bootstrap

Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx. 
  result = api_instance.get_bootstrap
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_bootstrap: #{e}"
end
```

#### Using the get_bootstrap_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_bootstrap_with_http_info

```ruby
begin
  # Single-shot identity + config bundle the renderer hits on first load. Replaces the legacy server-side hydration in app/layout.tsx. 
  data, status_code, headers = api_instance.get_bootstrap_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_bootstrap_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_onboarding_invitations

> Hash&lt;String, Object&gt; get_onboarding_invitations

Pending invitations the caller can accept during onboarding.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Pending invitations the caller can accept during onboarding.
  result = api_instance.get_onboarding_invitations
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_onboarding_invitations: #{e}"
end
```

#### Using the get_onboarding_invitations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_onboarding_invitations_with_http_info

```ruby
begin
  # Pending invitations the caller can accept during onboarding.
  data, status_code, headers = api_instance.get_onboarding_invitations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_onboarding_invitations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_pinned_platforms

> Hash&lt;String, Object&gt; get_pinned_platforms

Read the caller's pinned-platform list (sidebar order).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Read the caller's pinned-platform list (sidebar order).
  result = api_instance.get_pinned_platforms
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_pinned_platforms: #{e}"
end
```

#### Using the get_pinned_platforms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_pinned_platforms_with_http_info

```ruby
begin
  # Read the caller's pinned-platform list (sidebar order).
  data, status_code, headers = api_instance.get_pinned_platforms_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_pinned_platforms_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_platform_preferences

> Hash&lt;String, Object&gt; get_platform_preferences

Read the caller's per-platform sidebar/visibility preferences.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Read the caller's per-platform sidebar/visibility preferences.
  result = api_instance.get_platform_preferences
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_platform_preferences: #{e}"
end
```

#### Using the get_platform_preferences_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_platform_preferences_with_http_info

```ruby
begin
  # Read the caller's per-platform sidebar/visibility preferences.
  data, status_code, headers = api_instance.get_platform_preferences_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_platform_preferences_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_platform_settings_legacy

> Hash&lt;String, Object&gt; get_platform_settings_legacy

Legacy admin-tier platform settings read endpoint.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Legacy admin-tier platform settings read endpoint.
  result = api_instance.get_platform_settings_legacy
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_platform_settings_legacy: #{e}"
end
```

#### Using the get_platform_settings_legacy_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_platform_settings_legacy_with_http_info

```ruby
begin
  # Legacy admin-tier platform settings read endpoint.
  data, status_code, headers = api_instance.get_platform_settings_legacy_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_platform_settings_legacy_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_threads_status

> Hash&lt;String, Object&gt; get_threads_status

Async-thread / job-runner status snapshot.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Async-thread / job-runner status snapshot.
  result = api_instance.get_threads_status
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_threads_status: #{e}"
end
```

#### Using the get_threads_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_threads_status_with_http_info

```ruby
begin
  # Async-thread / job-runner status snapshot.
  data, status_code, headers = api_instance.get_threads_status_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_threads_status_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_user_permissions

> Hash&lt;String, Object&gt; get_user_permissions

Read the caller's effective per-resource permissions.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Read the caller's effective per-resource permissions.
  result = api_instance.get_user_permissions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_user_permissions: #{e}"
end
```

#### Using the get_user_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_user_permissions_with_http_info

```ruby
begin
  # Read the caller's effective per-resource permissions.
  data, status_code, headers = api_instance.get_user_permissions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_user_permissions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_workspace_activity

> Hash&lt;String, Object&gt; get_workspace_activity(opts)

Recent activity feed for a workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
opts = {
  workspace_id: 'workspace_id_example', # String | 
  limit: 56 # Integer | 
}

begin
  # Recent activity feed for a workspace.
  result = api_instance.get_workspace_activity(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_workspace_activity: #{e}"
end
```

#### Using the get_workspace_activity_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_workspace_activity_with_http_info(opts)

```ruby
begin
  # Recent activity feed for a workspace.
  data, status_code, headers = api_instance.get_workspace_activity_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_workspace_activity_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_workspace_layout

> Hash&lt;String, Object&gt; get_workspace_layout(workspace_id)

Read the renderer's saved pane layout for a workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
workspace_id = 'workspace_id_example' # String | 

begin
  # Read the renderer's saved pane layout for a workspace.
  result = api_instance.get_workspace_layout(workspace_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_workspace_layout: #{e}"
end
```

#### Using the get_workspace_layout_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_workspace_layout_with_http_info(workspace_id)

```ruby
begin
  # Read the renderer's saved pane layout for a workspace.
  data, status_code, headers = api_instance.get_workspace_layout_with_http_info(workspace_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->get_workspace_layout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## put_pinned_platform

> put_pinned_platform(request_body)

Pin a platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Pin a platform.
  api_instance.put_pinned_platform(request_body)
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_pinned_platform: #{e}"
end
```

#### Using the put_pinned_platform_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> put_pinned_platform_with_http_info(request_body)

```ruby
begin
  # Pin a platform.
  data, status_code, headers = api_instance.put_pinned_platform_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_pinned_platform_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## put_platform_preferences

> put_platform_preferences(request_body)

Replace the caller's platform preferences.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Replace the caller's platform preferences.
  api_instance.put_platform_preferences(request_body)
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_platform_preferences: #{e}"
end
```

#### Using the put_platform_preferences_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> put_platform_preferences_with_http_info(request_body)

```ruby
begin
  # Replace the caller's platform preferences.
  data, status_code, headers = api_instance.put_platform_preferences_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_platform_preferences_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## put_workspace_layout

> put_workspace_layout(workspace_id, request_body)

Save the renderer's pane layout.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
workspace_id = 'workspace_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Save the renderer's pane layout.
  api_instance.put_workspace_layout(workspace_id, request_body)
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_workspace_layout: #{e}"
end
```

#### Using the put_workspace_layout_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> put_workspace_layout_with_http_info(workspace_id, request_body)

```ruby
begin
  # Save the renderer's pane layout.
  data, status_code, headers = api_instance.put_workspace_layout_with_http_info(workspace_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->put_workspace_layout_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## reorder_pinned_platforms

> reorder_pinned_platforms(request_body)

Reorder the pinned-platform list.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Reorder the pinned-platform list.
  api_instance.reorder_pinned_platforms(request_body)
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->reorder_pinned_platforms: #{e}"
end
```

#### Using the reorder_pinned_platforms_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> reorder_pinned_platforms_with_http_info(request_body)

```ruby
begin
  # Reorder the pinned-platform list.
  data, status_code, headers = api_instance.reorder_pinned_platforms_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->reorder_pinned_platforms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## reset_platform_preferences

> reset_platform_preferences

Reset platform preferences to defaults.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new

begin
  # Reset platform preferences to defaults.
  api_instance.reset_platform_preferences
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->reset_platform_preferences: #{e}"
end
```

#### Using the reset_platform_preferences_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> reset_platform_preferences_with_http_info

```ruby
begin
  # Reset platform preferences to defaults.
  data, status_code, headers = api_instance.reset_platform_preferences_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->reset_platform_preferences_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_user_profile

> Hash&lt;String, Object&gt; update_user_profile(request_body)

Update the caller's user profile (name, avatar, etc.).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update the caller's user profile (name, avatar, etc.).
  result = api_instance.update_user_profile(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->update_user_profile: #{e}"
end
```

#### Using the update_user_profile_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_user_profile_with_http_info(request_body)

```ruby
begin
  # Update the caller's user profile (name, avatar, etc.).
  data, status_code, headers = api_instance.update_user_profile_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->update_user_profile_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## validate_organization_slug

> Hash&lt;String, Object&gt; validate_organization_slug(opts)

Check whether an org slug is available.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
opts = {
  slug: 'slug_example' # String | 
}

begin
  # Check whether an org slug is available.
  result = api_instance.validate_organization_slug(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->validate_organization_slug: #{e}"
end
```

#### Using the validate_organization_slug_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> validate_organization_slug_with_http_info(opts)

```ruby
begin
  # Check whether an org slug is available.
  data, status_code, headers = api_instance.validate_organization_slug_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->validate_organization_slug_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## validate_workspace_slug

> Hash&lt;String, Object&gt; validate_workspace_slug(opts)

Check whether a workspace slug is available.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MiscApi.new
opts = {
  slug: 'slug_example', # String | 
  organization_id: 'organization_id_example' # String | 
}

begin
  # Check whether a workspace slug is available.
  result = api_instance.validate_workspace_slug(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->validate_workspace_slug: #{e}"
end
```

#### Using the validate_workspace_slug_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> validate_workspace_slug_with_http_info(opts)

```ruby
begin
  # Check whether a workspace slug is available.
  data, status_code, headers = api_instance.validate_workspace_slug_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MiscApi->validate_workspace_slug_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

