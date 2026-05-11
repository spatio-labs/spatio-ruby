# Spatio::TerminalApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_terminal_session**](TerminalApi.md#create_terminal_session) | **POST** /v1/terminal/sessions | Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API.  |
| [**delete_terminal_session**](TerminalApi.md#delete_terminal_session) | **DELETE** /v1/terminal/sessions/{id} | Delete a terminal session record. |
| [**get_terminal_session**](TerminalApi.md#get_terminal_session) | **GET** /v1/terminal/sessions/{id} | Fetch a terminal session. |
| [**list_terminal_sessions**](TerminalApi.md#list_terminal_sessions) | **GET** /v1/terminal/sessions | List the caller&#39;s terminal sessions (metadata only — no PTY bytes). |
| [**update_terminal_session**](TerminalApi.md#update_terminal_session) | **PATCH** /v1/terminal/sessions/{id} | Update terminal session metadata (title, cwd, etc.). |


## create_terminal_session

> Hash&lt;String, Object&gt; create_terminal_session(request_body)

Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TerminalApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API. 
  result = api_instance.create_terminal_session(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->create_terminal_session: #{e}"
end
```

#### Using the create_terminal_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_terminal_session_with_http_info(request_body)

```ruby
begin
  # Create a terminal session record. PTY bytes flow renderer ↔ local-agent over IPC and never traverse this API. 
  data, status_code, headers = api_instance.create_terminal_session_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->create_terminal_session_with_http_info: #{e}"
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


## delete_terminal_session

> delete_terminal_session(id)

Delete a terminal session record.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TerminalApi.new
id = 'id_example' # String | 

begin
  # Delete a terminal session record.
  api_instance.delete_terminal_session(id)
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->delete_terminal_session: #{e}"
end
```

#### Using the delete_terminal_session_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_terminal_session_with_http_info(id)

```ruby
begin
  # Delete a terminal session record.
  data, status_code, headers = api_instance.delete_terminal_session_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->delete_terminal_session_with_http_info: #{e}"
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


## get_terminal_session

> Hash&lt;String, Object&gt; get_terminal_session(id)

Fetch a terminal session.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TerminalApi.new
id = 'id_example' # String | 

begin
  # Fetch a terminal session.
  result = api_instance.get_terminal_session(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->get_terminal_session: #{e}"
end
```

#### Using the get_terminal_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_terminal_session_with_http_info(id)

```ruby
begin
  # Fetch a terminal session.
  data, status_code, headers = api_instance.get_terminal_session_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->get_terminal_session_with_http_info: #{e}"
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


## list_terminal_sessions

> Hash&lt;String, Object&gt; list_terminal_sessions

List the caller's terminal sessions (metadata only — no PTY bytes).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TerminalApi.new

begin
  # List the caller's terminal sessions (metadata only — no PTY bytes).
  result = api_instance.list_terminal_sessions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->list_terminal_sessions: #{e}"
end
```

#### Using the list_terminal_sessions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_terminal_sessions_with_http_info

```ruby
begin
  # List the caller's terminal sessions (metadata only — no PTY bytes).
  data, status_code, headers = api_instance.list_terminal_sessions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->list_terminal_sessions_with_http_info: #{e}"
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


## update_terminal_session

> Hash&lt;String, Object&gt; update_terminal_session(id, request_body)

Update terminal session metadata (title, cwd, etc.).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TerminalApi.new
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update terminal session metadata (title, cwd, etc.).
  result = api_instance.update_terminal_session(id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->update_terminal_session: #{e}"
end
```

#### Using the update_terminal_session_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_terminal_session_with_http_info(id, request_body)

```ruby
begin
  # Update terminal session metadata (title, cwd, etc.).
  data, status_code, headers = api_instance.update_terminal_session_with_http_info(id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TerminalApi->update_terminal_session_with_http_info: #{e}"
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

