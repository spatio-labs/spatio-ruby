# Spatio::ConversationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_conversation**](ConversationsApi.md#create_conversation) | **POST** /v1/conversations | Persist a new LLM conversation. |
| [**delete_conversation**](ConversationsApi.md#delete_conversation) | **DELETE** /v1/conversations/{id} | Soft-delete a conversation. |
| [**get_conversation**](ConversationsApi.md#get_conversation) | **GET** /v1/conversations/{id} | Fetch one conversation. |
| [**get_latest_conversation_for_context**](ConversationsApi.md#get_latest_conversation_for_context) | **GET** /v1/conversations/latest | Fetch the most recently active conversation for a given context tag. |
| [**list_conversation_messages**](ConversationsApi.md#list_conversation_messages) | **GET** /v1/conversations/{id}/messages | List messages in a conversation. |
| [**list_conversations**](ConversationsApi.md#list_conversations) | **GET** /v1/conversations | List the caller&#39;s persisted LLM conversations. |
| [**save_conversation_message**](ConversationsApi.md#save_conversation_message) | **POST** /v1/conversations/{id}/messages | Append a message to a conversation. |
| [**update_conversation**](ConversationsApi.md#update_conversation) | **PATCH** /v1/conversations/{id} | Update conversation metadata (title, context, cwd, session_id, pinned). |
| [**update_conversation_message_metadata**](ConversationsApi.md#update_conversation_message_metadata) | **PATCH** /v1/conversations/{id}/messages | Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message).  |


## create_conversation

> <Conversation> create_conversation(opts)

Persist a new LLM conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
opts = {
  create_conversation_request: Spatio::CreateConversationRequest.new # CreateConversationRequest | 
}

begin
  # Persist a new LLM conversation.
  result = api_instance.create_conversation(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->create_conversation: #{e}"
end
```

#### Using the create_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Conversation>, Integer, Hash)> create_conversation_with_http_info(opts)

```ruby
begin
  # Persist a new LLM conversation.
  data, status_code, headers = api_instance.create_conversation_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Conversation>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->create_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_conversation_request** | [**CreateConversationRequest**](CreateConversationRequest.md) |  | [optional] |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_conversation

> delete_conversation(id)

Soft-delete a conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 

begin
  # Soft-delete a conversation.
  api_instance.delete_conversation(id)
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->delete_conversation: #{e}"
end
```

#### Using the delete_conversation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_conversation_with_http_info(id)

```ruby
begin
  # Soft-delete a conversation.
  data, status_code, headers = api_instance.delete_conversation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->delete_conversation_with_http_info: #{e}"
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


## get_conversation

> <Conversation> get_conversation(id)

Fetch one conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 

begin
  # Fetch one conversation.
  result = api_instance.get_conversation(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->get_conversation: #{e}"
end
```

#### Using the get_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Conversation>, Integer, Hash)> get_conversation_with_http_info(id)

```ruby
begin
  # Fetch one conversation.
  data, status_code, headers = api_instance.get_conversation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Conversation>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->get_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_latest_conversation_for_context

> <Conversation> get_latest_conversation_for_context(context)

Fetch the most recently active conversation for a given context tag.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
context = 'context_example' # String | 

begin
  # Fetch the most recently active conversation for a given context tag.
  result = api_instance.get_latest_conversation_for_context(context)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->get_latest_conversation_for_context: #{e}"
end
```

#### Using the get_latest_conversation_for_context_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Conversation>, Integer, Hash)> get_latest_conversation_for_context_with_http_info(context)

```ruby
begin
  # Fetch the most recently active conversation for a given context tag.
  data, status_code, headers = api_instance.get_latest_conversation_for_context_with_http_info(context)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Conversation>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->get_latest_conversation_for_context_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **context** | **String** |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_conversation_messages

> <Array<ConversationMessage>> list_conversation_messages(id, opts)

List messages in a conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 
opts = {
  limit: 56, # Integer | 
  before: 'before_example' # String | 
}

begin
  # List messages in a conversation.
  result = api_instance.list_conversation_messages(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->list_conversation_messages: #{e}"
end
```

#### Using the list_conversation_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Array<ConversationMessage>>, Integer, Hash)> list_conversation_messages_with_http_info(id, opts)

```ruby
begin
  # List messages in a conversation.
  data, status_code, headers = api_instance.list_conversation_messages_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Array<ConversationMessage>>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->list_conversation_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **limit** | **Integer** |  | [optional] |
| **before** | **String** |  | [optional] |

### Return type

[**Array&lt;ConversationMessage&gt;**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_conversations

> <Array<Conversation>> list_conversations(opts)

List the caller's persisted LLM conversations.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
opts = {
  context: 'context_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List the caller's persisted LLM conversations.
  result = api_instance.list_conversations(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->list_conversations: #{e}"
end
```

#### Using the list_conversations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Array<Conversation>>, Integer, Hash)> list_conversations_with_http_info(opts)

```ruby
begin
  # List the caller's persisted LLM conversations.
  data, status_code, headers = api_instance.list_conversations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Array<Conversation>>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->list_conversations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **context** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**Array&lt;Conversation&gt;**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## save_conversation_message

> <ConversationMessage> save_conversation_message(id, save_message_request)

Append a message to a conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 
save_message_request = Spatio::SaveMessageRequest.new({role: 'role_example', content: 'content_example'}) # SaveMessageRequest | 

begin
  # Append a message to a conversation.
  result = api_instance.save_conversation_message(id, save_message_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->save_conversation_message: #{e}"
end
```

#### Using the save_conversation_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConversationMessage>, Integer, Hash)> save_conversation_message_with_http_info(id, save_message_request)

```ruby
begin
  # Append a message to a conversation.
  data, status_code, headers = api_instance.save_conversation_message_with_http_info(id, save_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConversationMessage>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->save_conversation_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **save_message_request** | [**SaveMessageRequest**](SaveMessageRequest.md) |  |  |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_conversation

> <Conversation> update_conversation(id, update_conversation_request)

Update conversation metadata (title, context, cwd, session_id, pinned).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 
update_conversation_request = Spatio::UpdateConversationRequest.new # UpdateConversationRequest | 

begin
  # Update conversation metadata (title, context, cwd, session_id, pinned).
  result = api_instance.update_conversation(id, update_conversation_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->update_conversation: #{e}"
end
```

#### Using the update_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Conversation>, Integer, Hash)> update_conversation_with_http_info(id, update_conversation_request)

```ruby
begin
  # Update conversation metadata (title, context, cwd, session_id, pinned).
  data, status_code, headers = api_instance.update_conversation_with_http_info(id, update_conversation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Conversation>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->update_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_conversation_request** | [**UpdateConversationRequest**](UpdateConversationRequest.md) |  |  |

### Return type

[**Conversation**](Conversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_conversation_message_metadata

> <ConversationMessage> update_conversation_message_metadata(id, update_message_metadata_request)

Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ConversationsApi.new
id = 'id_example' # String | 
update_message_metadata_request = Spatio::UpdateMessageMetadataRequest.new({id: 'id_example'}) # UpdateMessageMetadataRequest | 

begin
  # Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 
  result = api_instance.update_conversation_message_metadata(id, update_message_metadata_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->update_conversation_message_metadata: #{e}"
end
```

#### Using the update_conversation_message_metadata_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ConversationMessage>, Integer, Hash)> update_conversation_message_metadata_with_http_info(id, update_message_metadata_request)

```ruby
begin
  # Patch metadata on an existing message. Body must include the message id (path is the conversation id, not the message). 
  data, status_code, headers = api_instance.update_conversation_message_metadata_with_http_info(id, update_message_metadata_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ConversationMessage>
rescue Spatio::ApiError => e
  puts "Error when calling ConversationsApi->update_conversation_message_metadata_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_message_metadata_request** | [**UpdateMessageMetadataRequest**](UpdateMessageMetadataRequest.md) |  |  |

### Return type

[**ConversationMessage**](ConversationMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

