# Spatio::ModelsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_model**](ModelsApi.md#create_model) | **POST** /v1/models | Register a model (admin-only). |
| [**delete_model**](ModelsApi.md#delete_model) | **DELETE** /v1/models/{id} | Delete a model (admin-only). |
| [**get_active_model**](ModelsApi.md#get_active_model) | **GET** /v1/models/active | Get the active model for a given provider. |
| [**get_model**](ModelsApi.md#get_model) | **GET** /v1/models/{id} | Fetch a model. |
| [**list_models**](ModelsApi.md#list_models) | **GET** /v1/models | List every LLM model the platform knows about. |
| [**set_active_model**](ModelsApi.md#set_active_model) | **POST** /v1/models/{id}/activate | Set a model as the active default for its provider (admin-only). |
| [**update_model**](ModelsApi.md#update_model) | **PATCH** /v1/models/{id} | Update a model (admin-only). |


## create_model

> Hash&lt;String, Object&gt; create_model(request_body)

Register a model (admin-only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Register a model (admin-only).
  result = api_instance.create_model(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->create_model: #{e}"
end
```

#### Using the create_model_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_model_with_http_info(request_body)

```ruby
begin
  # Register a model (admin-only).
  data, status_code, headers = api_instance.create_model_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->create_model_with_http_info: #{e}"
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


## delete_model

> delete_model(id)

Delete a model (admin-only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
id = 'id_example' # String | 

begin
  # Delete a model (admin-only).
  api_instance.delete_model(id)
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->delete_model: #{e}"
end
```

#### Using the delete_model_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_model_with_http_info(id)

```ruby
begin
  # Delete a model (admin-only).
  data, status_code, headers = api_instance.delete_model_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->delete_model_with_http_info: #{e}"
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


## get_active_model

> Hash&lt;String, Object&gt; get_active_model(opts)

Get the active model for a given provider.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
opts = {
  provider: 'provider_example' # String | 
}

begin
  # Get the active model for a given provider.
  result = api_instance.get_active_model(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->get_active_model: #{e}"
end
```

#### Using the get_active_model_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_active_model_with_http_info(opts)

```ruby
begin
  # Get the active model for a given provider.
  data, status_code, headers = api_instance.get_active_model_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->get_active_model_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_model

> Hash&lt;String, Object&gt; get_model(id)

Fetch a model.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
id = 'id_example' # String | 

begin
  # Fetch a model.
  result = api_instance.get_model(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->get_model: #{e}"
end
```

#### Using the get_model_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_model_with_http_info(id)

```ruby
begin
  # Fetch a model.
  data, status_code, headers = api_instance.get_model_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->get_model_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_models

> Hash&lt;String, Object&gt; list_models

List every LLM model the platform knows about.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new

begin
  # List every LLM model the platform knows about.
  result = api_instance.list_models
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->list_models: #{e}"
end
```

#### Using the list_models_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_models_with_http_info

```ruby
begin
  # List every LLM model the platform knows about.
  data, status_code, headers = api_instance.list_models_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->list_models_with_http_info: #{e}"
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


## set_active_model

> Hash&lt;String, Object&gt; set_active_model(id)

Set a model as the active default for its provider (admin-only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
id = 'id_example' # String | 

begin
  # Set a model as the active default for its provider (admin-only).
  result = api_instance.set_active_model(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->set_active_model: #{e}"
end
```

#### Using the set_active_model_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> set_active_model_with_http_info(id)

```ruby
begin
  # Set a model as the active default for its provider (admin-only).
  data, status_code, headers = api_instance.set_active_model_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->set_active_model_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_model

> Hash&lt;String, Object&gt; update_model(id, request_body)

Update a model (admin-only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ModelsApi.new
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update a model (admin-only).
  result = api_instance.update_model(id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->update_model: #{e}"
end
```

#### Using the update_model_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_model_with_http_info(id, request_body)

```ruby
begin
  # Update a model (admin-only).
  data, status_code, headers = api_instance.update_model_with_http_info(id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ModelsApi->update_model_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

