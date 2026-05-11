# Spatio::ActionsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**execute_action**](ActionsApi.md#execute_action) | **POST** /v1/actions/execute | Renderer-side execute alias. The canonical endpoint is &#x60;POST /v1/agent/actions/execute&#x60;; this path delegates to the same handler.  |
| [**get_core_action**](ActionsApi.md#get_core_action) | **GET** /v1/actions/core/{id} | Fetch a single core action by id. |
| [**list_available_actions**](ActionsApi.md#list_available_actions) | **GET** /v1/actions/available | List every action the agent platform exposes. |
| [**list_core_actions**](ActionsApi.md#list_core_actions) | **GET** /v1/actions/core | List renderer-curated \&quot;core actions\&quot; (command-palette + keybindings backing). |
| [**list_core_actions_by_platform**](ActionsApi.md#list_core_actions_by_platform) | **GET** /v1/actions/core/platform/{platform} | Core actions filtered to one platform. |
| [**list_platform_actions**](ActionsApi.md#list_platform_actions) | **GET** /v1/actions/platform/{platform} | List actions tagged for a specific platform (notes, mail, ...). |


## execute_action

> <ExecuteActionResponse> execute_action(execute_action_request)

Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new
execute_action_request = Spatio::ExecuteActionRequest.new({action_id: 'action_id_example'}) # ExecuteActionRequest | 

begin
  # Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 
  result = api_instance.execute_action(execute_action_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->execute_action: #{e}"
end
```

#### Using the execute_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExecuteActionResponse>, Integer, Hash)> execute_action_with_http_info(execute_action_request)

```ruby
begin
  # Renderer-side execute alias. The canonical endpoint is `POST /v1/agent/actions/execute`; this path delegates to the same handler. 
  data, status_code, headers = api_instance.execute_action_with_http_info(execute_action_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExecuteActionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->execute_action_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **execute_action_request** | [**ExecuteActionRequest**](ExecuteActionRequest.md) |  |  |

### Return type

[**ExecuteActionResponse**](ExecuteActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_core_action

> <CoreAction> get_core_action(id)

Fetch a single core action by id.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new
id = 'id_example' # String | 

begin
  # Fetch a single core action by id.
  result = api_instance.get_core_action(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->get_core_action: #{e}"
end
```

#### Using the get_core_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CoreAction>, Integer, Hash)> get_core_action_with_http_info(id)

```ruby
begin
  # Fetch a single core action by id.
  data, status_code, headers = api_instance.get_core_action_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CoreAction>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->get_core_action_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**CoreAction**](CoreAction.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_available_actions

> <Array<ActionDescriptor>> list_available_actions

List every action the agent platform exposes.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new

begin
  # List every action the agent platform exposes.
  result = api_instance.list_available_actions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_available_actions: #{e}"
end
```

#### Using the list_available_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Array<ActionDescriptor>>, Integer, Hash)> list_available_actions_with_http_info

```ruby
begin
  # List every action the agent platform exposes.
  data, status_code, headers = api_instance.list_available_actions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Array<ActionDescriptor>>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_available_actions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Array&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_core_actions

> <CoreActionListResponse> list_core_actions

List renderer-curated \"core actions\" (command-palette + keybindings backing).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new

begin
  # List renderer-curated \"core actions\" (command-palette + keybindings backing).
  result = api_instance.list_core_actions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_core_actions: #{e}"
end
```

#### Using the list_core_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CoreActionListResponse>, Integer, Hash)> list_core_actions_with_http_info

```ruby
begin
  # List renderer-curated \"core actions\" (command-palette + keybindings backing).
  data, status_code, headers = api_instance.list_core_actions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CoreActionListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_core_actions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_core_actions_by_platform

> <CoreActionListResponse> list_core_actions_by_platform(platform)

Core actions filtered to one platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new
platform = 'platform_example' # String | 

begin
  # Core actions filtered to one platform.
  result = api_instance.list_core_actions_by_platform(platform)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_core_actions_by_platform: #{e}"
end
```

#### Using the list_core_actions_by_platform_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CoreActionListResponse>, Integer, Hash)> list_core_actions_by_platform_with_http_info(platform)

```ruby
begin
  # Core actions filtered to one platform.
  data, status_code, headers = api_instance.list_core_actions_by_platform_with_http_info(platform)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CoreActionListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_core_actions_by_platform_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  |  |

### Return type

[**CoreActionListResponse**](CoreActionListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platform_actions

> <Array<ActionDescriptor>> list_platform_actions(platform)

List actions tagged for a specific platform (notes, mail, ...).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ActionsApi.new
platform = 'platform_example' # String | 

begin
  # List actions tagged for a specific platform (notes, mail, ...).
  result = api_instance.list_platform_actions(platform)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_platform_actions: #{e}"
end
```

#### Using the list_platform_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Array<ActionDescriptor>>, Integer, Hash)> list_platform_actions_with_http_info(platform)

```ruby
begin
  # List actions tagged for a specific platform (notes, mail, ...).
  data, status_code, headers = api_instance.list_platform_actions_with_http_info(platform)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Array<ActionDescriptor>>
rescue Spatio::ApiError => e
  puts "Error when calling ActionsApi->list_platform_actions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  |  |

### Return type

[**Array&lt;ActionDescriptor&gt;**](ActionDescriptor.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

