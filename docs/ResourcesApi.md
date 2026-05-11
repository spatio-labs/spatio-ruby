# Spatio::ResourcesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**list_resource_permission_grants**](ResourcesApi.md#list_resource_permission_grants) | **GET** /v1/resources/{platform}/{resourceId}/permissions | List access grants on a resource (per-resource ACL). |
| [**revoke_resource_permission_grant**](ResourcesApi.md#revoke_resource_permission_grant) | **DELETE** /v1/resources/{platform}/{resourceId}/permissions/{grantId} | Revoke an access grant. |
| [**set_resource_permission_grant**](ResourcesApi.md#set_resource_permission_grant) | **POST** /v1/resources/{platform}/{resourceId}/permissions | Create or update an access grant. |


## list_resource_permission_grants

> Hash&lt;String, Object&gt; list_resource_permission_grants(platform, resource_id)

List access grants on a resource (per-resource ACL).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ResourcesApi.new
platform = 'platform_example' # String | 
resource_id = 'resource_id_example' # String | 

begin
  # List access grants on a resource (per-resource ACL).
  result = api_instance.list_resource_permission_grants(platform, resource_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->list_resource_permission_grants: #{e}"
end
```

#### Using the list_resource_permission_grants_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_resource_permission_grants_with_http_info(platform, resource_id)

```ruby
begin
  # List access grants on a resource (per-resource ACL).
  data, status_code, headers = api_instance.list_resource_permission_grants_with_http_info(platform, resource_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->list_resource_permission_grants_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  |  |
| **resource_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_resource_permission_grant

> revoke_resource_permission_grant(platform, resource_id, grant_id)

Revoke an access grant.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ResourcesApi.new
platform = 'platform_example' # String | 
resource_id = 'resource_id_example' # String | 
grant_id = 'grant_id_example' # String | 

begin
  # Revoke an access grant.
  api_instance.revoke_resource_permission_grant(platform, resource_id, grant_id)
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->revoke_resource_permission_grant: #{e}"
end
```

#### Using the revoke_resource_permission_grant_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_resource_permission_grant_with_http_info(platform, resource_id, grant_id)

```ruby
begin
  # Revoke an access grant.
  data, status_code, headers = api_instance.revoke_resource_permission_grant_with_http_info(platform, resource_id, grant_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->revoke_resource_permission_grant_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  |  |
| **resource_id** | **String** |  |  |
| **grant_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## set_resource_permission_grant

> Hash&lt;String, Object&gt; set_resource_permission_grant(platform, resource_id, request_body)

Create or update an access grant.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ResourcesApi.new
platform = 'platform_example' # String | 
resource_id = 'resource_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create or update an access grant.
  result = api_instance.set_resource_permission_grant(platform, resource_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->set_resource_permission_grant: #{e}"
end
```

#### Using the set_resource_permission_grant_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> set_resource_permission_grant_with_http_info(platform, resource_id, request_body)

```ruby
begin
  # Create or update an access grant.
  data, status_code, headers = api_instance.set_resource_permission_grant_with_http_info(platform, resource_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ResourcesApi->set_resource_permission_grant_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  |  |
| **resource_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

