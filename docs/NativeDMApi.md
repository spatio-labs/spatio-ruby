# Spatio::NativeDMApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_native_dm_reaction**](NativeDMApi.md#add_native_dm_reaction) | **POST** /v1/native/dm/messages/{messageId}/reactions | Add a reaction to a DM message. |
| [**attach_to_native_dm_message**](NativeDMApi.md#attach_to_native_dm_message) | **POST** /v1/native/dm/messages/{messageId}/attachments | Attach a file to a DM message. |
| [**delete_native_dm_message**](NativeDMApi.md#delete_native_dm_message) | **DELETE** /v1/native/dm/{dmId}/messages/{messageId} | Delete a DM message. |
| [**forward_native_dm_message**](NativeDMApi.md#forward_native_dm_message) | **POST** /v1/native/dm/messages/{messageId}/forward | Forward a DM message to another conversation. |
| [**list_native_dm_channels**](NativeDMApi.md#list_native_dm_channels) | **GET** /v1/native/dm | List the caller&#39;s DM channels. |
| [**list_native_dm_conversations**](NativeDMApi.md#list_native_dm_conversations) | **GET** /v1/native/dm/conversations | List DM conversations with metadata (last message, unread count, etc.). |
| [**list_native_dm_messages**](NativeDMApi.md#list_native_dm_messages) | **GET** /v1/native/dm/{dmId}/messages | List messages in a DM. |
| [**list_native_dm_pinned_messages**](NativeDMApi.md#list_native_dm_pinned_messages) | **GET** /v1/native/dm/{dmId}/pinned | List pinned messages in a DM. |
| [**list_native_dm_thread_replies**](NativeDMApi.md#list_native_dm_thread_replies) | **GET** /v1/native/dm/{dmId}/messages/{messageId}/replies | List threaded replies on a message. |
| [**mark_native_dm_read**](NativeDMApi.md#mark_native_dm_read) | **POST** /v1/native/dm/{dmId}/read | Mark a DM as read. |
| [**mute_native_dm**](NativeDMApi.md#mute_native_dm) | **POST** /v1/native/dm/{dmId}/mute | Mute a DM. |
| [**pin_native_dm_conversation**](NativeDMApi.md#pin_native_dm_conversation) | **POST** /v1/native/dm/{dmId}/pin | Pin a DM conversation in the sidebar. |
| [**pin_native_dm_message**](NativeDMApi.md#pin_native_dm_message) | **POST** /v1/native/dm/messages/{messageId}/pin | Pin a DM message. |
| [**post_native_dm_message**](NativeDMApi.md#post_native_dm_message) | **POST** /v1/native/dm | Post a DM message (top-level entry). |
| [**post_native_dm_thread_reply**](NativeDMApi.md#post_native_dm_thread_reply) | **POST** /v1/native/dm/{dmId}/messages/{messageId}/replies | Post a threaded reply. |
| [**remove_native_dm_reaction**](NativeDMApi.md#remove_native_dm_reaction) | **DELETE** /v1/native/dm/messages/{messageId}/reactions/{emoji} | Remove a reaction. |
| [**search_native_dm_messages**](NativeDMApi.md#search_native_dm_messages) | **GET** /v1/native/dm/search | Search DM messages. |
| [**set_native_dm_draft**](NativeDMApi.md#set_native_dm_draft) | **PUT** /v1/native/dm/{dmId}/draft | Save a draft on a DM conversation. |
| [**unpin_native_dm_conversation**](NativeDMApi.md#unpin_native_dm_conversation) | **DELETE** /v1/native/dm/{dmId}/pin | Unpin a DM conversation. |
| [**unpin_native_dm_message**](NativeDMApi.md#unpin_native_dm_message) | **DELETE** /v1/native/dm/messages/{messageId}/pin | Unpin a DM message. |
| [**update_native_dm_message**](NativeDMApi.md#update_native_dm_message) | **PATCH** /v1/native/dm/{dmId}/messages/{messageId} | Update a DM message body. |


## add_native_dm_reaction

> Hash&lt;String, Object&gt; add_native_dm_reaction(message_id, request_body)

Add a reaction to a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Add a reaction to a DM message.
  result = api_instance.add_native_dm_reaction(message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->add_native_dm_reaction: #{e}"
end
```

#### Using the add_native_dm_reaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> add_native_dm_reaction_with_http_info(message_id, request_body)

```ruby
begin
  # Add a reaction to a DM message.
  data, status_code, headers = api_instance.add_native_dm_reaction_with_http_info(message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->add_native_dm_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## attach_to_native_dm_message

> Hash&lt;String, Object&gt; attach_to_native_dm_message(message_id, request_body)

Attach a file to a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Attach a file to a DM message.
  result = api_instance.attach_to_native_dm_message(message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->attach_to_native_dm_message: #{e}"
end
```

#### Using the attach_to_native_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> attach_to_native_dm_message_with_http_info(message_id, request_body)

```ruby
begin
  # Attach a file to a DM message.
  data, status_code, headers = api_instance.attach_to_native_dm_message_with_http_info(message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->attach_to_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_native_dm_message

> delete_native_dm_message(dm_id, message_id)

Delete a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
message_id = 'message_id_example' # String | 

begin
  # Delete a DM message.
  api_instance.delete_native_dm_message(dm_id, message_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->delete_native_dm_message: #{e}"
end
```

#### Using the delete_native_dm_message_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_native_dm_message_with_http_info(dm_id, message_id)

```ruby
begin
  # Delete a DM message.
  data, status_code, headers = api_instance.delete_native_dm_message_with_http_info(dm_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->delete_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## forward_native_dm_message

> Hash&lt;String, Object&gt; forward_native_dm_message(message_id, request_body)

Forward a DM message to another conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Forward a DM message to another conversation.
  result = api_instance.forward_native_dm_message(message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->forward_native_dm_message: #{e}"
end
```

#### Using the forward_native_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> forward_native_dm_message_with_http_info(message_id, request_body)

```ruby
begin
  # Forward a DM message to another conversation.
  data, status_code, headers = api_instance.forward_native_dm_message_with_http_info(message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->forward_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_native_dm_channels

> Hash&lt;String, Object&gt; list_native_dm_channels

List the caller's DM channels.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new

begin
  # List the caller's DM channels.
  result = api_instance.list_native_dm_channels
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_channels: #{e}"
end
```

#### Using the list_native_dm_channels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_native_dm_channels_with_http_info

```ruby
begin
  # List the caller's DM channels.
  data, status_code, headers = api_instance.list_native_dm_channels_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_channels_with_http_info: #{e}"
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


## list_native_dm_conversations

> Hash&lt;String, Object&gt; list_native_dm_conversations

List DM conversations with metadata (last message, unread count, etc.).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new

begin
  # List DM conversations with metadata (last message, unread count, etc.).
  result = api_instance.list_native_dm_conversations
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_conversations: #{e}"
end
```

#### Using the list_native_dm_conversations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_native_dm_conversations_with_http_info

```ruby
begin
  # List DM conversations with metadata (last message, unread count, etc.).
  data, status_code, headers = api_instance.list_native_dm_conversations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_conversations_with_http_info: #{e}"
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


## list_native_dm_messages

> Hash&lt;String, Object&gt; list_native_dm_messages(dm_id)

List messages in a DM.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 

begin
  # List messages in a DM.
  result = api_instance.list_native_dm_messages(dm_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_messages: #{e}"
end
```

#### Using the list_native_dm_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_native_dm_messages_with_http_info(dm_id)

```ruby
begin
  # List messages in a DM.
  data, status_code, headers = api_instance.list_native_dm_messages_with_http_info(dm_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_native_dm_pinned_messages

> Hash&lt;String, Object&gt; list_native_dm_pinned_messages(dm_id)

List pinned messages in a DM.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 

begin
  # List pinned messages in a DM.
  result = api_instance.list_native_dm_pinned_messages(dm_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_pinned_messages: #{e}"
end
```

#### Using the list_native_dm_pinned_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_native_dm_pinned_messages_with_http_info(dm_id)

```ruby
begin
  # List pinned messages in a DM.
  data, status_code, headers = api_instance.list_native_dm_pinned_messages_with_http_info(dm_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_pinned_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_native_dm_thread_replies

> Hash&lt;String, Object&gt; list_native_dm_thread_replies(dm_id, message_id)

List threaded replies on a message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
message_id = 'message_id_example' # String | 

begin
  # List threaded replies on a message.
  result = api_instance.list_native_dm_thread_replies(dm_id, message_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_thread_replies: #{e}"
end
```

#### Using the list_native_dm_thread_replies_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_native_dm_thread_replies_with_http_info(dm_id, message_id)

```ruby
begin
  # List threaded replies on a message.
  data, status_code, headers = api_instance.list_native_dm_thread_replies_with_http_info(dm_id, message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->list_native_dm_thread_replies_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **message_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_native_dm_read

> mark_native_dm_read(dm_id)

Mark a DM as read.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 

begin
  # Mark a DM as read.
  api_instance.mark_native_dm_read(dm_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->mark_native_dm_read: #{e}"
end
```

#### Using the mark_native_dm_read_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> mark_native_dm_read_with_http_info(dm_id)

```ruby
begin
  # Mark a DM as read.
  data, status_code, headers = api_instance.mark_native_dm_read_with_http_info(dm_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->mark_native_dm_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mute_native_dm

> mute_native_dm(dm_id, opts)

Mute a DM.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  # Mute a DM.
  api_instance.mute_native_dm(dm_id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->mute_native_dm: #{e}"
end
```

#### Using the mute_native_dm_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> mute_native_dm_with_http_info(dm_id, opts)

```ruby
begin
  # Mute a DM.
  data, status_code, headers = api_instance.mute_native_dm_with_http_info(dm_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->mute_native_dm_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## pin_native_dm_conversation

> pin_native_dm_conversation(dm_id)

Pin a DM conversation in the sidebar.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 

begin
  # Pin a DM conversation in the sidebar.
  api_instance.pin_native_dm_conversation(dm_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->pin_native_dm_conversation: #{e}"
end
```

#### Using the pin_native_dm_conversation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> pin_native_dm_conversation_with_http_info(dm_id)

```ruby
begin
  # Pin a DM conversation in the sidebar.
  data, status_code, headers = api_instance.pin_native_dm_conversation_with_http_info(dm_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->pin_native_dm_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## pin_native_dm_message

> pin_native_dm_message(message_id)

Pin a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 

begin
  # Pin a DM message.
  api_instance.pin_native_dm_message(message_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->pin_native_dm_message: #{e}"
end
```

#### Using the pin_native_dm_message_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> pin_native_dm_message_with_http_info(message_id)

```ruby
begin
  # Pin a DM message.
  data, status_code, headers = api_instance.pin_native_dm_message_with_http_info(message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->pin_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## post_native_dm_message

> Hash&lt;String, Object&gt; post_native_dm_message(request_body)

Post a DM message (top-level entry).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Post a DM message (top-level entry).
  result = api_instance.post_native_dm_message(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->post_native_dm_message: #{e}"
end
```

#### Using the post_native_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> post_native_dm_message_with_http_info(request_body)

```ruby
begin
  # Post a DM message (top-level entry).
  data, status_code, headers = api_instance.post_native_dm_message_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->post_native_dm_message_with_http_info: #{e}"
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


## post_native_dm_thread_reply

> Hash&lt;String, Object&gt; post_native_dm_thread_reply(dm_id, message_id, request_body)

Post a threaded reply.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Post a threaded reply.
  result = api_instance.post_native_dm_thread_reply(dm_id, message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->post_native_dm_thread_reply: #{e}"
end
```

#### Using the post_native_dm_thread_reply_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> post_native_dm_thread_reply_with_http_info(dm_id, message_id, request_body)

```ruby
begin
  # Post a threaded reply.
  data, status_code, headers = api_instance.post_native_dm_thread_reply_with_http_info(dm_id, message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->post_native_dm_thread_reply_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_native_dm_reaction

> remove_native_dm_reaction(message_id, emoji)

Remove a reaction.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 
emoji = 'emoji_example' # String | 

begin
  # Remove a reaction.
  api_instance.remove_native_dm_reaction(message_id, emoji)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->remove_native_dm_reaction: #{e}"
end
```

#### Using the remove_native_dm_reaction_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_native_dm_reaction_with_http_info(message_id, emoji)

```ruby
begin
  # Remove a reaction.
  data, status_code, headers = api_instance.remove_native_dm_reaction_with_http_info(message_id, emoji)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->remove_native_dm_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **emoji** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## search_native_dm_messages

> Hash&lt;String, Object&gt; search_native_dm_messages(opts)

Search DM messages.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
opts = {
  q: 'q_example' # String | 
}

begin
  # Search DM messages.
  result = api_instance.search_native_dm_messages(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->search_native_dm_messages: #{e}"
end
```

#### Using the search_native_dm_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> search_native_dm_messages_with_http_info(opts)

```ruby
begin
  # Search DM messages.
  data, status_code, headers = api_instance.search_native_dm_messages_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->search_native_dm_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **q** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## set_native_dm_draft

> set_native_dm_draft(dm_id, request_body)

Save a draft on a DM conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Save a draft on a DM conversation.
  api_instance.set_native_dm_draft(dm_id, request_body)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->set_native_dm_draft: #{e}"
end
```

#### Using the set_native_dm_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> set_native_dm_draft_with_http_info(dm_id, request_body)

```ruby
begin
  # Save a draft on a DM conversation.
  data, status_code, headers = api_instance.set_native_dm_draft_with_http_info(dm_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->set_native_dm_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## unpin_native_dm_conversation

> unpin_native_dm_conversation(dm_id)

Unpin a DM conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 

begin
  # Unpin a DM conversation.
  api_instance.unpin_native_dm_conversation(dm_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->unpin_native_dm_conversation: #{e}"
end
```

#### Using the unpin_native_dm_conversation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> unpin_native_dm_conversation_with_http_info(dm_id)

```ruby
begin
  # Unpin a DM conversation.
  data, status_code, headers = api_instance.unpin_native_dm_conversation_with_http_info(dm_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->unpin_native_dm_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## unpin_native_dm_message

> unpin_native_dm_message(message_id)

Unpin a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
message_id = 'message_id_example' # String | 

begin
  # Unpin a DM message.
  api_instance.unpin_native_dm_message(message_id)
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->unpin_native_dm_message: #{e}"
end
```

#### Using the unpin_native_dm_message_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> unpin_native_dm_message_with_http_info(message_id)

```ruby
begin
  # Unpin a DM message.
  data, status_code, headers = api_instance.unpin_native_dm_message_with_http_info(message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->unpin_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_native_dm_message

> Hash&lt;String, Object&gt; update_native_dm_message(dm_id, message_id, request_body)

Update a DM message body.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NativeDMApi.new
dm_id = 'dm_id_example' # String | 
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update a DM message body.
  result = api_instance.update_native_dm_message(dm_id, message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->update_native_dm_message: #{e}"
end
```

#### Using the update_native_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_native_dm_message_with_http_info(dm_id, message_id, request_body)

```ruby
begin
  # Update a DM message body.
  data, status_code, headers = api_instance.update_native_dm_message_with_http_info(dm_id, message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NativeDMApi->update_native_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

