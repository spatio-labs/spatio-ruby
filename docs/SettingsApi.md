# Spatio::SettingsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**bulk_update_settings**](SettingsApi.md#bulk_update_settings) | **POST** /v1/settings/bulk-update | Bulk-update multiple settings rows in one round-trip. |
| [**delete_current_user_settings**](SettingsApi.md#delete_current_user_settings) | **DELETE** /v1/settings | Reset the caller&#39;s user-level settings. |
| [**get_current_user_settings**](SettingsApi.md#get_current_user_settings) | **GET** /v1/settings | Fetch the caller&#39;s user-level settings. |
| [**get_mail_read_receipts_pref**](SettingsApi.md#get_mail_read_receipts_pref) | **GET** /v1/me/preferences/mail-read-receipts | Read the caller&#39;s mail-read-receipts preference. |
| [**get_settings_permissions**](SettingsApi.md#get_settings_permissions) | **GET** /v1/settings/permissions | Read the caller&#39;s settings-write permissions matrix. |
| [**get_user_settings**](SettingsApi.md#get_user_settings) | **GET** /v1/settings/user/{userId} | Fetch a specific user&#39;s settings (admin / self only). |
| [**get_workspace_settings**](SettingsApi.md#get_workspace_settings) | **GET** /v1/settings/workspace/{workspaceId} | Fetch workspace-level settings. |
| [**put_current_user_settings**](SettingsApi.md#put_current_user_settings) | **PUT** /v1/settings | Replace the caller&#39;s user-level settings. |
| [**put_mail_read_receipts_pref**](SettingsApi.md#put_mail_read_receipts_pref) | **PUT** /v1/me/preferences/mail-read-receipts | Update the caller&#39;s mail-read-receipts preference. |
| [**put_user_settings**](SettingsApi.md#put_user_settings) | **PUT** /v1/settings/user/{userId} | Replace a specific user&#39;s settings. |
| [**put_workspace_settings**](SettingsApi.md#put_workspace_settings) | **PUT** /v1/settings/workspace/{workspaceId} | Replace workspace-level settings. |


## bulk_update_settings

> Hash&lt;String, Object&gt; bulk_update_settings(request_body)

Bulk-update multiple settings rows in one round-trip.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Bulk-update multiple settings rows in one round-trip.
  result = api_instance.bulk_update_settings(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->bulk_update_settings: #{e}"
end
```

#### Using the bulk_update_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> bulk_update_settings_with_http_info(request_body)

```ruby
begin
  # Bulk-update multiple settings rows in one round-trip.
  data, status_code, headers = api_instance.bulk_update_settings_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->bulk_update_settings_with_http_info: #{e}"
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


## delete_current_user_settings

> delete_current_user_settings

Reset the caller's user-level settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new

begin
  # Reset the caller's user-level settings.
  api_instance.delete_current_user_settings
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->delete_current_user_settings: #{e}"
end
```

#### Using the delete_current_user_settings_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_current_user_settings_with_http_info

```ruby
begin
  # Reset the caller's user-level settings.
  data, status_code, headers = api_instance.delete_current_user_settings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->delete_current_user_settings_with_http_info: #{e}"
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


## get_current_user_settings

> Hash&lt;String, Object&gt; get_current_user_settings

Fetch the caller's user-level settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new

begin
  # Fetch the caller's user-level settings.
  result = api_instance.get_current_user_settings
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_current_user_settings: #{e}"
end
```

#### Using the get_current_user_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_current_user_settings_with_http_info

```ruby
begin
  # Fetch the caller's user-level settings.
  data, status_code, headers = api_instance.get_current_user_settings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_current_user_settings_with_http_info: #{e}"
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


## get_mail_read_receipts_pref

> Hash&lt;String, Object&gt; get_mail_read_receipts_pref

Read the caller's mail-read-receipts preference.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new

begin
  # Read the caller's mail-read-receipts preference.
  result = api_instance.get_mail_read_receipts_pref
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_mail_read_receipts_pref: #{e}"
end
```

#### Using the get_mail_read_receipts_pref_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_mail_read_receipts_pref_with_http_info

```ruby
begin
  # Read the caller's mail-read-receipts preference.
  data, status_code, headers = api_instance.get_mail_read_receipts_pref_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_mail_read_receipts_pref_with_http_info: #{e}"
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


## get_settings_permissions

> Hash&lt;String, Object&gt; get_settings_permissions

Read the caller's settings-write permissions matrix.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new

begin
  # Read the caller's settings-write permissions matrix.
  result = api_instance.get_settings_permissions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_settings_permissions: #{e}"
end
```

#### Using the get_settings_permissions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_settings_permissions_with_http_info

```ruby
begin
  # Read the caller's settings-write permissions matrix.
  data, status_code, headers = api_instance.get_settings_permissions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_settings_permissions_with_http_info: #{e}"
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


## get_user_settings

> Hash&lt;String, Object&gt; get_user_settings(user_id)

Fetch a specific user's settings (admin / self only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
user_id = 'user_id_example' # String | 

begin
  # Fetch a specific user's settings (admin / self only).
  result = api_instance.get_user_settings(user_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_user_settings: #{e}"
end
```

#### Using the get_user_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_user_settings_with_http_info(user_id)

```ruby
begin
  # Fetch a specific user's settings (admin / self only).
  data, status_code, headers = api_instance.get_user_settings_with_http_info(user_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_user_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_workspace_settings

> Hash&lt;String, Object&gt; get_workspace_settings(workspace_id)

Fetch workspace-level settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
workspace_id = 'workspace_id_example' # String | 

begin
  # Fetch workspace-level settings.
  result = api_instance.get_workspace_settings(workspace_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_workspace_settings: #{e}"
end
```

#### Using the get_workspace_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_workspace_settings_with_http_info(workspace_id)

```ruby
begin
  # Fetch workspace-level settings.
  data, status_code, headers = api_instance.get_workspace_settings_with_http_info(workspace_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->get_workspace_settings_with_http_info: #{e}"
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


## put_current_user_settings

> Hash&lt;String, Object&gt; put_current_user_settings(request_body)

Replace the caller's user-level settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Replace the caller's user-level settings.
  result = api_instance.put_current_user_settings(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_current_user_settings: #{e}"
end
```

#### Using the put_current_user_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> put_current_user_settings_with_http_info(request_body)

```ruby
begin
  # Replace the caller's user-level settings.
  data, status_code, headers = api_instance.put_current_user_settings_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_current_user_settings_with_http_info: #{e}"
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


## put_mail_read_receipts_pref

> put_mail_read_receipts_pref(request_body)

Update the caller's mail-read-receipts preference.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update the caller's mail-read-receipts preference.
  api_instance.put_mail_read_receipts_pref(request_body)
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_mail_read_receipts_pref: #{e}"
end
```

#### Using the put_mail_read_receipts_pref_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> put_mail_read_receipts_pref_with_http_info(request_body)

```ruby
begin
  # Update the caller's mail-read-receipts preference.
  data, status_code, headers = api_instance.put_mail_read_receipts_pref_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_mail_read_receipts_pref_with_http_info: #{e}"
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


## put_user_settings

> Hash&lt;String, Object&gt; put_user_settings(user_id, request_body)

Replace a specific user's settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
user_id = 'user_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Replace a specific user's settings.
  result = api_instance.put_user_settings(user_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_user_settings: #{e}"
end
```

#### Using the put_user_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> put_user_settings_with_http_info(user_id, request_body)

```ruby
begin
  # Replace a specific user's settings.
  data, status_code, headers = api_instance.put_user_settings_with_http_info(user_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_user_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## put_workspace_settings

> Hash&lt;String, Object&gt; put_workspace_settings(workspace_id, request_body)

Replace workspace-level settings.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SettingsApi.new
workspace_id = 'workspace_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Replace workspace-level settings.
  result = api_instance.put_workspace_settings(workspace_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_workspace_settings: #{e}"
end
```

#### Using the put_workspace_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> put_workspace_settings_with_http_info(workspace_id, request_body)

```ruby
begin
  # Replace workspace-level settings.
  data, status_code, headers = api_instance.put_workspace_settings_with_http_info(workspace_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SettingsApi->put_workspace_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

