# Spatio::InboxApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_inbox_counts**](InboxApi.md#get_inbox_counts) | **GET** /v1/inbox/counts | Per-bucket unread counts. |
| [**list_inbox**](InboxApi.md#list_inbox) | **GET** /v1/inbox | Unified inbox feed across mail, channel mentions, DMs, system notifications. |
| [**mark_inbox_item_read**](InboxApi.md#mark_inbox_item_read) | **PATCH** /v1/inbox/{id}/read | Mark a single inbox item as read. |
| [**workspace_get_inbox_counts**](InboxApi.md#workspace_get_inbox_counts) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox/counts |  |
| [**workspace_list_inbox**](InboxApi.md#workspace_list_inbox) | **GET** /v1/organizations/{org}/workspaces/{workspace}/inbox |  |
| [**workspace_mark_inbox_item_read**](InboxApi.md#workspace_mark_inbox_item_read) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/inbox/{id}/read |  |


## get_inbox_counts

> <InboxCounts> get_inbox_counts

Per-bucket unread counts.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new

begin
  # Per-bucket unread counts.
  result = api_instance.get_inbox_counts
  p result
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->get_inbox_counts: #{e}"
end
```

#### Using the get_inbox_counts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InboxCounts>, Integer, Hash)> get_inbox_counts_with_http_info

```ruby
begin
  # Per-bucket unread counts.
  data, status_code, headers = api_instance.get_inbox_counts_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InboxCounts>
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->get_inbox_counts_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**InboxCounts**](InboxCounts.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_inbox

> <InboxListResponse> list_inbox(opts)

Unified inbox feed across mail, channel mentions, DMs, system notifications.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new
opts = {
  category: 'category_example', # String | 
  unread_only: true, # Boolean | 
  limit: 56 # Integer | 
}

begin
  # Unified inbox feed across mail, channel mentions, DMs, system notifications.
  result = api_instance.list_inbox(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->list_inbox: #{e}"
end
```

#### Using the list_inbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InboxListResponse>, Integer, Hash)> list_inbox_with_http_info(opts)

```ruby
begin
  # Unified inbox feed across mail, channel mentions, DMs, system notifications.
  data, status_code, headers = api_instance.list_inbox_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InboxListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->list_inbox_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category** | **String** |  | [optional] |
| **unread_only** | **Boolean** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**InboxListResponse**](InboxListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_inbox_item_read

> mark_inbox_item_read(id)

Mark a single inbox item as read.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new
id = 'id_example' # String | 

begin
  # Mark a single inbox item as read.
  api_instance.mark_inbox_item_read(id)
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->mark_inbox_item_read: #{e}"
end
```

#### Using the mark_inbox_item_read_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> mark_inbox_item_read_with_http_info(id)

```ruby
begin
  # Mark a single inbox item as read.
  data, status_code, headers = api_instance.mark_inbox_item_read_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->mark_inbox_item_read_with_http_info: #{e}"
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


## workspace_get_inbox_counts

> Hash&lt;String, Object&gt; workspace_get_inbox_counts(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_get_inbox_counts(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_get_inbox_counts: #{e}"
end
```

#### Using the workspace_get_inbox_counts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_inbox_counts_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_inbox_counts_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_get_inbox_counts_with_http_info: #{e}"
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


## workspace_list_inbox

> Hash&lt;String, Object&gt; workspace_list_inbox(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_inbox(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_list_inbox: #{e}"
end
```

#### Using the workspace_list_inbox_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_inbox_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_inbox_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_list_inbox_with_http_info: #{e}"
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


## workspace_mark_inbox_item_read

> workspace_mark_inbox_item_read(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::InboxApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_mark_inbox_item_read(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_mark_inbox_item_read: #{e}"
end
```

#### Using the workspace_mark_inbox_item_read_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_mark_inbox_item_read_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_mark_inbox_item_read_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling InboxApi->workspace_mark_inbox_item_read_with_http_info: #{e}"
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

