# Spatio::NavigationApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_navigation**](NavigationApi.md#get_navigation) | **GET** /v1/navigation | Sidebar/navigation tree for the renderer. |


## get_navigation

> Hash&lt;String, Object&gt; get_navigation

Sidebar/navigation tree for the renderer.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NavigationApi.new

begin
  # Sidebar/navigation tree for the renderer.
  result = api_instance.get_navigation
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NavigationApi->get_navigation: #{e}"
end
```

#### Using the get_navigation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_navigation_with_http_info

```ruby
begin
  # Sidebar/navigation tree for the renderer.
  data, status_code, headers = api_instance.get_navigation_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NavigationApi->get_navigation_with_http_info: #{e}"
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

