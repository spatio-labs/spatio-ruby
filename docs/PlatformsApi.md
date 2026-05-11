# Spatio::PlatformsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_platform_provider_account**](PlatformsApi.md#add_platform_provider_account) | **POST** /v1/platforms/{platformId}/providers/{provider}/accounts | Add a connected account for a platform/provider pair. |
| [**create_or_update_platform_secret**](PlatformsApi.md#create_or_update_platform_secret) | **POST** /v1/platforms/{platformId}/secrets | Create or update a secret value. |
| [**delete_platform_secret**](PlatformsApi.md#delete_platform_secret) | **DELETE** /v1/platforms/{platformId}/secrets/{name} | Delete a secret. |
| [**exec_platform_data**](PlatformsApi.md#exec_platform_data) | **POST** /v1/platforms/{platformId}/exec | Run an INSERT/UPDATE/DELETE statement against a platform&#39;s store. |
| [**export_platform_secrets**](PlatformsApi.md#export_platform_secrets) | **GET** /v1/platforms/{platformId}/secrets/export | Export all secrets for a platform (values included). Caller must be the platform owner.  |
| [**generate_platform_backend_token**](PlatformsApi.md#generate_platform_backend_token) | **POST** /v1/platforms/{platformId}/backend-token | Generate a short-lived backend JWT a platform&#39;s worker can use to call back into platform-service.  |
| [**get_platform_catalog**](PlatformsApi.md#get_platform_catalog) | **GET** /v1/catalog/platforms | List the global platform catalog — every platform that exists, not just the ones the caller has installed.  |
| [**get_platform_manifest**](PlatformsApi.md#get_platform_manifest) | **GET** /v1/platforms/{platformId}/manifest | Fetch a platform&#39;s manifest (capabilities, schema, UI metadata). |
| [**list_platform_accounts**](PlatformsApi.md#list_platform_accounts) | **GET** /v1/platforms/{platformId}/accounts | List accounts the caller has connected for a platform. |
| [**list_platform_providers**](PlatformsApi.md#list_platform_providers) | **GET** /v1/platforms/{platformId}/providers | Discover supported providers + capabilities for a platform. |
| [**list_platform_secrets**](PlatformsApi.md#list_platform_secrets) | **GET** /v1/platforms/{platformId}/secrets | List secret keys (values redacted). |
| [**list_platform_tables**](PlatformsApi.md#list_platform_tables) | **GET** /v1/platforms/{platformId}/tables | List tables in a platform&#39;s data store. |
| [**list_platforms**](PlatformsApi.md#list_platforms) | **GET** /v1/platforms | List installed platforms for the sidebar. |
| [**query_platform_data**](PlatformsApi.md#query_platform_data) | **POST** /v1/platforms/{platformId}/query | Run a SELECT query against a platform&#39;s data store. |
| [**run_platform_migrations**](PlatformsApi.md#run_platform_migrations) | **POST** /v1/platforms/{platformId}/migrate | Run pending migrations for a platform. |


## add_platform_provider_account

> Hash&lt;String, Object&gt; add_platform_provider_account(platform_id, provider, request_body)

Add a connected account for a platform/provider pair.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 
provider = 'provider_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Add a connected account for a platform/provider pair.
  result = api_instance.add_platform_provider_account(platform_id, provider, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->add_platform_provider_account: #{e}"
end
```

#### Using the add_platform_provider_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> add_platform_provider_account_with_http_info(platform_id, provider, request_body)

```ruby
begin
  # Add a connected account for a platform/provider pair.
  data, status_code, headers = api_instance.add_platform_provider_account_with_http_info(platform_id, provider, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->add_platform_provider_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |
| **provider** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_or_update_platform_secret

> Hash&lt;String, Object&gt; create_or_update_platform_secret(platform_id, request_body)

Create or update a secret value.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create or update a secret value.
  result = api_instance.create_or_update_platform_secret(platform_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->create_or_update_platform_secret: #{e}"
end
```

#### Using the create_or_update_platform_secret_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_or_update_platform_secret_with_http_info(platform_id, request_body)

```ruby
begin
  # Create or update a secret value.
  data, status_code, headers = api_instance.create_or_update_platform_secret_with_http_info(platform_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->create_or_update_platform_secret_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_platform_secret

> delete_platform_secret(platform_id, name)

Delete a secret.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 
name = 'name_example' # String | 

begin
  # Delete a secret.
  api_instance.delete_platform_secret(platform_id, name)
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->delete_platform_secret: #{e}"
end
```

#### Using the delete_platform_secret_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_platform_secret_with_http_info(platform_id, name)

```ruby
begin
  # Delete a secret.
  data, status_code, headers = api_instance.delete_platform_secret_with_http_info(platform_id, name)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->delete_platform_secret_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |
| **name** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## exec_platform_data

> Hash&lt;String, Object&gt; exec_platform_data(platform_id, request_body)

Run an INSERT/UPDATE/DELETE statement against a platform's store.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Run an INSERT/UPDATE/DELETE statement against a platform's store.
  result = api_instance.exec_platform_data(platform_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->exec_platform_data: #{e}"
end
```

#### Using the exec_platform_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> exec_platform_data_with_http_info(platform_id, request_body)

```ruby
begin
  # Run an INSERT/UPDATE/DELETE statement against a platform's store.
  data, status_code, headers = api_instance.exec_platform_data_with_http_info(platform_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->exec_platform_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_platform_secrets

> Hash&lt;String, Object&gt; export_platform_secrets(platform_id)

Export all secrets for a platform (values included). Caller must be the platform owner. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Export all secrets for a platform (values included). Caller must be the platform owner. 
  result = api_instance.export_platform_secrets(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->export_platform_secrets: #{e}"
end
```

#### Using the export_platform_secrets_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> export_platform_secrets_with_http_info(platform_id)

```ruby
begin
  # Export all secrets for a platform (values included). Caller must be the platform owner. 
  data, status_code, headers = api_instance.export_platform_secrets_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->export_platform_secrets_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## generate_platform_backend_token

> Hash&lt;String, Object&gt; generate_platform_backend_token(platform_id)

Generate a short-lived backend JWT a platform's worker can use to call back into platform-service. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Generate a short-lived backend JWT a platform's worker can use to call back into platform-service. 
  result = api_instance.generate_platform_backend_token(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->generate_platform_backend_token: #{e}"
end
```

#### Using the generate_platform_backend_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> generate_platform_backend_token_with_http_info(platform_id)

```ruby
begin
  # Generate a short-lived backend JWT a platform's worker can use to call back into platform-service. 
  data, status_code, headers = api_instance.generate_platform_backend_token_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->generate_platform_backend_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_platform_catalog

> Hash&lt;String, Object&gt; get_platform_catalog

List the global platform catalog — every platform that exists, not just the ones the caller has installed. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new

begin
  # List the global platform catalog — every platform that exists, not just the ones the caller has installed. 
  result = api_instance.get_platform_catalog
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->get_platform_catalog: #{e}"
end
```

#### Using the get_platform_catalog_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_platform_catalog_with_http_info

```ruby
begin
  # List the global platform catalog — every platform that exists, not just the ones the caller has installed. 
  data, status_code, headers = api_instance.get_platform_catalog_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->get_platform_catalog_with_http_info: #{e}"
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


## get_platform_manifest

> Hash&lt;String, Object&gt; get_platform_manifest(platform_id)

Fetch a platform's manifest (capabilities, schema, UI metadata).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Fetch a platform's manifest (capabilities, schema, UI metadata).
  result = api_instance.get_platform_manifest(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->get_platform_manifest: #{e}"
end
```

#### Using the get_platform_manifest_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_platform_manifest_with_http_info(platform_id)

```ruby
begin
  # Fetch a platform's manifest (capabilities, schema, UI metadata).
  data, status_code, headers = api_instance.get_platform_manifest_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->get_platform_manifest_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platform_accounts

> Hash&lt;String, Object&gt; list_platform_accounts(platform_id)

List accounts the caller has connected for a platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # List accounts the caller has connected for a platform.
  result = api_instance.list_platform_accounts(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_accounts: #{e}"
end
```

#### Using the list_platform_accounts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_platform_accounts_with_http_info(platform_id)

```ruby
begin
  # List accounts the caller has connected for a platform.
  data, status_code, headers = api_instance.list_platform_accounts_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_accounts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platform_providers

> Hash&lt;String, Object&gt; list_platform_providers(platform_id)

Discover supported providers + capabilities for a platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Discover supported providers + capabilities for a platform.
  result = api_instance.list_platform_providers(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_providers: #{e}"
end
```

#### Using the list_platform_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_platform_providers_with_http_info(platform_id)

```ruby
begin
  # Discover supported providers + capabilities for a platform.
  data, status_code, headers = api_instance.list_platform_providers_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_providers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platform_secrets

> Hash&lt;String, Object&gt; list_platform_secrets(platform_id)

List secret keys (values redacted).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # List secret keys (values redacted).
  result = api_instance.list_platform_secrets(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_secrets: #{e}"
end
```

#### Using the list_platform_secrets_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_platform_secrets_with_http_info(platform_id)

```ruby
begin
  # List secret keys (values redacted).
  data, status_code, headers = api_instance.list_platform_secrets_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_secrets_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platform_tables

> Hash&lt;String, Object&gt; list_platform_tables(platform_id)

List tables in a platform's data store.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # List tables in a platform's data store.
  result = api_instance.list_platform_tables(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_tables: #{e}"
end
```

#### Using the list_platform_tables_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_platform_tables_with_http_info(platform_id)

```ruby
begin
  # List tables in a platform's data store.
  data, status_code, headers = api_instance.list_platform_tables_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platform_tables_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_platforms

> Hash&lt;String, Object&gt; list_platforms

List installed platforms for the sidebar.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new

begin
  # List installed platforms for the sidebar.
  result = api_instance.list_platforms
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platforms: #{e}"
end
```

#### Using the list_platforms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_platforms_with_http_info

```ruby
begin
  # List installed platforms for the sidebar.
  data, status_code, headers = api_instance.list_platforms_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->list_platforms_with_http_info: #{e}"
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


## query_platform_data

> Hash&lt;String, Object&gt; query_platform_data(platform_id, request_body)

Run a SELECT query against a platform's data store.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Run a SELECT query against a platform's data store.
  result = api_instance.query_platform_data(platform_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->query_platform_data: #{e}"
end
```

#### Using the query_platform_data_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> query_platform_data_with_http_info(platform_id, request_body)

```ruby
begin
  # Run a SELECT query against a platform's data store.
  data, status_code, headers = api_instance.query_platform_data_with_http_info(platform_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->query_platform_data_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## run_platform_migrations

> Hash&lt;String, Object&gt; run_platform_migrations(platform_id)

Run pending migrations for a platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::PlatformsApi.new
platform_id = 'platform_id_example' # String | 

begin
  # Run pending migrations for a platform.
  result = api_instance.run_platform_migrations(platform_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->run_platform_migrations: #{e}"
end
```

#### Using the run_platform_migrations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> run_platform_migrations_with_http_info(platform_id)

```ruby
begin
  # Run pending migrations for a platform.
  data, status_code, headers = api_instance.run_platform_migrations_with_http_info(platform_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling PlatformsApi->run_platform_migrations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

