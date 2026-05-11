# Spatio::NotificationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_notification_preferences**](NotificationsApi.md#get_notification_preferences) | **GET** /v1/notifications/preferences | Read the caller&#39;s notification preferences. |
| [**update_notification_preferences**](NotificationsApi.md#update_notification_preferences) | **PATCH** /v1/notifications/preferences | Update notification preferences. |


## get_notification_preferences

> Hash&lt;String, Object&gt; get_notification_preferences

Read the caller's notification preferences.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotificationsApi.new

begin
  # Read the caller's notification preferences.
  result = api_instance.get_notification_preferences
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotificationsApi->get_notification_preferences: #{e}"
end
```

#### Using the get_notification_preferences_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_notification_preferences_with_http_info

```ruby
begin
  # Read the caller's notification preferences.
  data, status_code, headers = api_instance.get_notification_preferences_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotificationsApi->get_notification_preferences_with_http_info: #{e}"
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


## update_notification_preferences

> Hash&lt;String, Object&gt; update_notification_preferences(request_body)

Update notification preferences.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotificationsApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update notification preferences.
  result = api_instance.update_notification_preferences(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotificationsApi->update_notification_preferences: #{e}"
end
```

#### Using the update_notification_preferences_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_notification_preferences_with_http_info(request_body)

```ruby
begin
  # Update notification preferences.
  data, status_code, headers = api_instance.update_notification_preferences_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotificationsApi->update_notification_preferences_with_http_info: #{e}"
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

