# Spatio::KeybindingsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_key_binding**](KeybindingsApi.md#delete_key_binding) | **DELETE** /v1/keybindings/{id} | Reset a binding to its platform default. |
| [**get_default_key_bindings**](KeybindingsApi.md#get_default_key_bindings) | **GET** /v1/keybindings/defaults | Platform default key bindings (no user customizations applied). |
| [**list_key_bindings**](KeybindingsApi.md#list_key_bindings) | **GET** /v1/keybindings | User&#39;s merged key bindings (defaults + customizations). |
| [**reset_all_key_bindings**](KeybindingsApi.md#reset_all_key_bindings) | **POST** /v1/keybindings/reset | Reset every customization to its platform default. |
| [**update_key_binding**](KeybindingsApi.md#update_key_binding) | **PUT** /v1/keybindings/{id} | Create or update a user key-binding customization. |
| [**validate_key_binding**](KeybindingsApi.md#validate_key_binding) | **POST** /v1/keybindings/validate | Check whether a proposed binding conflicts with existing ones. |


## delete_key_binding

> delete_key_binding(id)

Reset a binding to its platform default.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new
id = 'id_example' # String | 

begin
  # Reset a binding to its platform default.
  api_instance.delete_key_binding(id)
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->delete_key_binding: #{e}"
end
```

#### Using the delete_key_binding_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_key_binding_with_http_info(id)

```ruby
begin
  # Reset a binding to its platform default.
  data, status_code, headers = api_instance.delete_key_binding_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->delete_key_binding_with_http_info: #{e}"
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


## get_default_key_bindings

> <KeyBindingListResponse> get_default_key_bindings

Platform default key bindings (no user customizations applied).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new

begin
  # Platform default key bindings (no user customizations applied).
  result = api_instance.get_default_key_bindings
  p result
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->get_default_key_bindings: #{e}"
end
```

#### Using the get_default_key_bindings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<KeyBindingListResponse>, Integer, Hash)> get_default_key_bindings_with_http_info

```ruby
begin
  # Platform default key bindings (no user customizations applied).
  data, status_code, headers = api_instance.get_default_key_bindings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <KeyBindingListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->get_default_key_bindings_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_key_bindings

> <KeyBindingListResponse> list_key_bindings

User's merged key bindings (defaults + customizations).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new

begin
  # User's merged key bindings (defaults + customizations).
  result = api_instance.list_key_bindings
  p result
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->list_key_bindings: #{e}"
end
```

#### Using the list_key_bindings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<KeyBindingListResponse>, Integer, Hash)> list_key_bindings_with_http_info

```ruby
begin
  # User's merged key bindings (defaults + customizations).
  data, status_code, headers = api_instance.list_key_bindings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <KeyBindingListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->list_key_bindings_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**KeyBindingListResponse**](KeyBindingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## reset_all_key_bindings

> reset_all_key_bindings

Reset every customization to its platform default.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new

begin
  # Reset every customization to its platform default.
  api_instance.reset_all_key_bindings
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->reset_all_key_bindings: #{e}"
end
```

#### Using the reset_all_key_bindings_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> reset_all_key_bindings_with_http_info

```ruby
begin
  # Reset every customization to its platform default.
  data, status_code, headers = api_instance.reset_all_key_bindings_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->reset_all_key_bindings_with_http_info: #{e}"
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


## update_key_binding

> <KeyBinding> update_key_binding(id, update_key_binding_request)

Create or update a user key-binding customization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new
id = 'id_example' # String | 
update_key_binding_request = Spatio::UpdateKeyBindingRequest.new({key: 'key_example'}) # UpdateKeyBindingRequest | 

begin
  # Create or update a user key-binding customization.
  result = api_instance.update_key_binding(id, update_key_binding_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->update_key_binding: #{e}"
end
```

#### Using the update_key_binding_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<KeyBinding>, Integer, Hash)> update_key_binding_with_http_info(id, update_key_binding_request)

```ruby
begin
  # Create or update a user key-binding customization.
  data, status_code, headers = api_instance.update_key_binding_with_http_info(id, update_key_binding_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <KeyBinding>
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->update_key_binding_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_key_binding_request** | [**UpdateKeyBindingRequest**](UpdateKeyBindingRequest.md) |  |  |

### Return type

[**KeyBinding**](KeyBinding.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## validate_key_binding

> <ValidateKeyBindingResponse> validate_key_binding(validate_key_binding_request)

Check whether a proposed binding conflicts with existing ones.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::KeybindingsApi.new
validate_key_binding_request = Spatio::ValidateKeyBindingRequest.new({action_id: 'action_id_example', key: 'key_example'}) # ValidateKeyBindingRequest | 

begin
  # Check whether a proposed binding conflicts with existing ones.
  result = api_instance.validate_key_binding(validate_key_binding_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->validate_key_binding: #{e}"
end
```

#### Using the validate_key_binding_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ValidateKeyBindingResponse>, Integer, Hash)> validate_key_binding_with_http_info(validate_key_binding_request)

```ruby
begin
  # Check whether a proposed binding conflicts with existing ones.
  data, status_code, headers = api_instance.validate_key_binding_with_http_info(validate_key_binding_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ValidateKeyBindingResponse>
rescue Spatio::ApiError => e
  puts "Error when calling KeybindingsApi->validate_key_binding_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **validate_key_binding_request** | [**ValidateKeyBindingRequest**](ValidateKeyBindingRequest.md) |  |  |

### Return type

[**ValidateKeyBindingResponse**](ValidateKeyBindingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

