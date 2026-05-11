# Spatio::AppsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_app**](AppsApi.md#create_app) | **POST** /v1/apps | Register a prototype app (project_path is the on-disk root). |
| [**delete_app**](AppsApi.md#delete_app) | **DELETE** /v1/apps/{id} | Delete an app. |
| [**delete_app_file**](AppsApi.md#delete_app_file) | **DELETE** /v1/apps/{id}/file | Delete one file inside the app&#39;s project directory. |
| [**get_app**](AppsApi.md#get_app) | **GET** /v1/apps/{id} | Fetch an app. |
| [**list_app_files**](AppsApi.md#list_app_files) | **GET** /v1/apps/{id}/files | List files inside the app&#39;s project directory. |
| [**list_apps**](AppsApi.md#list_apps) | **GET** /v1/apps | List the caller&#39;s prototype apps. |
| [**read_app_file**](AppsApi.md#read_app_file) | **GET** /v1/apps/{id}/file | Read one file inside the app&#39;s project directory. Path is traversal-checked; returns 400 if it escapes project root.  |
| [**update_app**](AppsApi.md#update_app) | **PATCH** /v1/apps/{id} | Update an app. |
| [**workspace_create_app**](AppsApi.md#workspace_create_app) | **POST** /v1/organizations/{org}/workspaces/{workspace}/apps |  |
| [**workspace_delete_app**](AppsApi.md#workspace_delete_app) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**workspace_get_app**](AppsApi.md#workspace_get_app) | **GET** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**workspace_list_apps**](AppsApi.md#workspace_list_apps) | **GET** /v1/organizations/{org}/workspaces/{workspace}/apps |  |
| [**workspace_update_app**](AppsApi.md#workspace_update_app) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/apps/{id} |  |
| [**write_app_file**](AppsApi.md#write_app_file) | **POST** /v1/apps/{id}/file | Write one file inside the app&#39;s project directory. |


## create_app

> <App> create_app(create_app_request)

Register a prototype app (project_path is the on-disk root).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
create_app_request = Spatio::CreateAppRequest.new({name: 'name_example'}) # CreateAppRequest | 

begin
  # Register a prototype app (project_path is the on-disk root).
  result = api_instance.create_app(create_app_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->create_app: #{e}"
end
```

#### Using the create_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<App>, Integer, Hash)> create_app_with_http_info(create_app_request)

```ruby
begin
  # Register a prototype app (project_path is the on-disk root).
  data, status_code, headers = api_instance.create_app_with_http_info(create_app_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <App>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->create_app_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_app_request** | [**CreateAppRequest**](CreateAppRequest.md) |  |  |

### Return type

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_app

> delete_app(id)

Delete an app.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 

begin
  # Delete an app.
  api_instance.delete_app(id)
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->delete_app: #{e}"
end
```

#### Using the delete_app_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_app_with_http_info(id)

```ruby
begin
  # Delete an app.
  data, status_code, headers = api_instance.delete_app_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->delete_app_with_http_info: #{e}"
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


## delete_app_file

> delete_app_file(id, path)

Delete one file inside the app's project directory.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 
path = 'path_example' # String | 

begin
  # Delete one file inside the app's project directory.
  api_instance.delete_app_file(id, path)
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->delete_app_file: #{e}"
end
```

#### Using the delete_app_file_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_app_file_with_http_info(id, path)

```ruby
begin
  # Delete one file inside the app's project directory.
  data, status_code, headers = api_instance.delete_app_file_with_http_info(id, path)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->delete_app_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **path** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_app

> <App> get_app(id)

Fetch an app.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 

begin
  # Fetch an app.
  result = api_instance.get_app(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->get_app: #{e}"
end
```

#### Using the get_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<App>, Integer, Hash)> get_app_with_http_info(id)

```ruby
begin
  # Fetch an app.
  data, status_code, headers = api_instance.get_app_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <App>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->get_app_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_app_files

> <AppFileListResponse> list_app_files(id, opts)

List files inside the app's project directory.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 
opts = {
  path: 'path_example' # String | 
}

begin
  # List files inside the app's project directory.
  result = api_instance.list_app_files(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->list_app_files: #{e}"
end
```

#### Using the list_app_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AppFileListResponse>, Integer, Hash)> list_app_files_with_http_info(id, opts)

```ruby
begin
  # List files inside the app's project directory.
  data, status_code, headers = api_instance.list_app_files_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AppFileListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->list_app_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **path** | **String** |  | [optional] |

### Return type

[**AppFileListResponse**](AppFileListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_apps

> <AppListResponse> list_apps

List the caller's prototype apps.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new

begin
  # List the caller's prototype apps.
  result = api_instance.list_apps
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->list_apps: #{e}"
end
```

#### Using the list_apps_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AppListResponse>, Integer, Hash)> list_apps_with_http_info

```ruby
begin
  # List the caller's prototype apps.
  data, status_code, headers = api_instance.list_apps_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AppListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->list_apps_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AppListResponse**](AppListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## read_app_file

> <AppFileContentResponse> read_app_file(id, path)

Read one file inside the app's project directory. Path is traversal-checked; returns 400 if it escapes project root. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 
path = 'path_example' # String | 

begin
  # Read one file inside the app's project directory. Path is traversal-checked; returns 400 if it escapes project root. 
  result = api_instance.read_app_file(id, path)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->read_app_file: #{e}"
end
```

#### Using the read_app_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AppFileContentResponse>, Integer, Hash)> read_app_file_with_http_info(id, path)

```ruby
begin
  # Read one file inside the app's project directory. Path is traversal-checked; returns 400 if it escapes project root. 
  data, status_code, headers = api_instance.read_app_file_with_http_info(id, path)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AppFileContentResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->read_app_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **path** | **String** |  |  |

### Return type

[**AppFileContentResponse**](AppFileContentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_app

> <App> update_app(id, update_app_request)

Update an app.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 
update_app_request = Spatio::UpdateAppRequest.new # UpdateAppRequest | 

begin
  # Update an app.
  result = api_instance.update_app(id, update_app_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->update_app: #{e}"
end
```

#### Using the update_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<App>, Integer, Hash)> update_app_with_http_info(id, update_app_request)

```ruby
begin
  # Update an app.
  data, status_code, headers = api_instance.update_app_with_http_info(id, update_app_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <App>
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->update_app_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_app_request** | [**UpdateAppRequest**](UpdateAppRequest.md) |  |  |

### Return type

[**App**](App.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_app

> Hash&lt;String, Object&gt; workspace_create_app(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_app(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_create_app: #{e}"
end
```

#### Using the workspace_create_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_app_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_app_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_create_app_with_http_info: #{e}"
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


## workspace_delete_app

> workspace_delete_app(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_app(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_delete_app: #{e}"
end
```

#### Using the workspace_delete_app_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_app_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_app_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_delete_app_with_http_info: #{e}"
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


## workspace_get_app

> Hash&lt;String, Object&gt; workspace_get_app(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_app(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_get_app: #{e}"
end
```

#### Using the workspace_get_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_app_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_app_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_get_app_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_apps

> Hash&lt;String, Object&gt; workspace_list_apps(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_apps(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_list_apps: #{e}"
end
```

#### Using the workspace_list_apps_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_apps_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_apps_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_list_apps_with_http_info: #{e}"
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


## workspace_update_app

> Hash&lt;String, Object&gt; workspace_update_app(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_app(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_update_app: #{e}"
end
```

#### Using the workspace_update_app_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_app_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_app_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->workspace_update_app_with_http_info: #{e}"
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


## write_app_file

> write_app_file(id, write_app_file_request)

Write one file inside the app's project directory.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AppsApi.new
id = 'id_example' # String | 
write_app_file_request = Spatio::WriteAppFileRequest.new({path: 'path_example', content: 'content_example'}) # WriteAppFileRequest | 

begin
  # Write one file inside the app's project directory.
  api_instance.write_app_file(id, write_app_file_request)
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->write_app_file: #{e}"
end
```

#### Using the write_app_file_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> write_app_file_with_http_info(id, write_app_file_request)

```ruby
begin
  # Write one file inside the app's project directory.
  data, status_code, headers = api_instance.write_app_file_with_http_info(id, write_app_file_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AppsApi->write_app_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **write_app_file_request** | [**WriteAppFileRequest**](WriteAppFileRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

