# Spatio::DirectMessagesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_dm_reaction**](DirectMessagesApi.md#add_dm_reaction) | **POST** /v1/direct-messages/messages/{messageId}/reactions | React to a DM message. |
| [**attach_to_dm_message**](DirectMessagesApi.md#attach_to_dm_message) | **POST** /v1/direct-messages/messages/{messageId}/attachments | Attach a file/image/etc. to an existing DM message. |
| [**execute_dm_action**](DirectMessagesApi.md#execute_dm_action) | **POST** /v1/direct-messages/execute | Dispatch a DM action by id. |
| [**forward_dm_message**](DirectMessagesApi.md#forward_dm_message) | **POST** /v1/direct-messages/messages/{messageId}/forward | Forward a DM message to another DM or channel. |
| [**get_dm_user**](DirectMessagesApi.md#get_dm_user) | **GET** /v1/direct-messages/users/{id} | Fetch one chat user. |
| [**list_direct_conversations_enriched**](DirectMessagesApi.md#list_direct_conversations_enriched) | **GET** /v1/direct-messages/conversations | Enriched DM conversation list with unread + pin + draft state. |
| [**list_direct_message_conversations**](DirectMessagesApi.md#list_direct_message_conversations) | **GET** /v1/direct-messages | List 1:1 and group DM conversations. |
| [**list_direct_messages**](DirectMessagesApi.md#list_direct_messages) | **GET** /v1/direct-messages/messages | List messages in a DM conversation. |
| [**list_dm_actions**](DirectMessagesApi.md#list_dm_actions) | **GET** /v1/direct-messages/actions | Discover the action catalog for DirectMessages. |
| [**list_dm_pinned_messages**](DirectMessagesApi.md#list_dm_pinned_messages) | **GET** /v1/direct-messages/{dmId}/pinned | List pinned messages in a DM conversation. |
| [**list_dm_thread_replies**](DirectMessagesApi.md#list_dm_thread_replies) | **GET** /v1/direct-messages/{dmId}/messages/{messageId}/replies | List replies in a DM message thread. |
| [**list_dm_users**](DirectMessagesApi.md#list_dm_users) | **GET** /v1/direct-messages/users | List chat users (DM contacts) across connected accounts. |
| [**mark_dm_read**](DirectMessagesApi.md#mark_dm_read) | **POST** /v1/direct-messages/{dmId}/read | Mark a DM message read. |
| [**mute_dm**](DirectMessagesApi.md#mute_dm) | **POST** /v1/direct-messages/{dmId}/mute | Mute a DM conversation (until a time, or forever). |
| [**pin_dm_conversation**](DirectMessagesApi.md#pin_dm_conversation) | **POST** /v1/direct-messages/{dmId}/pin | Pin a DM conversation to the top of the sidebar. |
| [**pin_dm_message**](DirectMessagesApi.md#pin_dm_message) | **POST** /v1/direct-messages/messages/{messageId}/pin | Pin a DM message. |
| [**post_dm_thread_reply**](DirectMessagesApi.md#post_dm_thread_reply) | **POST** /v1/direct-messages/{dmId}/messages/{messageId}/replies | Reply in a DM message thread. |
| [**remove_dm_reaction**](DirectMessagesApi.md#remove_dm_reaction) | **DELETE** /v1/direct-messages/messages/{messageId}/reactions/{emoji} | Remove a DM message reaction. |
| [**search_direct_messages**](DirectMessagesApi.md#search_direct_messages) | **GET** /v1/direct-messages/search | Search across DM messages. |
| [**send_direct_message**](DirectMessagesApi.md#send_direct_message) | **POST** /v1/direct-messages/messages | Send a DM. |
| [**set_dm_draft**](DirectMessagesApi.md#set_dm_draft) | **PUT** /v1/direct-messages/{dmId}/draft | Save the unsent draft text for a DM. |
| [**unpin_dm_conversation**](DirectMessagesApi.md#unpin_dm_conversation) | **DELETE** /v1/direct-messages/{dmId}/pin | Unpin a DM conversation. |
| [**unpin_dm_message**](DirectMessagesApi.md#unpin_dm_message) | **DELETE** /v1/direct-messages/messages/{messageId}/pin | Unpin a DM message. |
| [**workspace_execute_dm_action**](DirectMessagesApi.md#workspace_execute_dm_action) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/execute |  |
| [**workspace_get_dm_user**](DirectMessagesApi.md#workspace_get_dm_user) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users/{id} |  |
| [**workspace_list_direct_messages**](DirectMessagesApi.md#workspace_list_direct_messages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages |  |
| [**workspace_list_dm_actions**](DirectMessagesApi.md#workspace_list_dm_actions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/actions |  |
| [**workspace_list_dm_conversations**](DirectMessagesApi.md#workspace_list_dm_conversations) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/conversations |  |
| [**workspace_list_dm_messages**](DirectMessagesApi.md#workspace_list_dm_messages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |
| [**workspace_list_dm_users**](DirectMessagesApi.md#workspace_list_dm_users) | **GET** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/users |  |
| [**workspace_send_direct_message**](DirectMessagesApi.md#workspace_send_direct_message) | **POST** /v1/organizations/{org}/workspaces/{workspace}/direct-messages/messages |  |


## add_dm_reaction

> <DMReactionResponse> add_dm_reaction(message_id, dm_reaction_request)

React to a DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
dm_reaction_request = Spatio::DMReactionRequest.new({emoji: 'emoji_example'}) # DMReactionRequest | 

begin
  # React to a DM message.
  result = api_instance.add_dm_reaction(message_id, dm_reaction_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->add_dm_reaction: #{e}"
end
```

#### Using the add_dm_reaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMReactionResponse>, Integer, Hash)> add_dm_reaction_with_http_info(message_id, dm_reaction_request)

```ruby
begin
  # React to a DM message.
  data, status_code, headers = api_instance.add_dm_reaction_with_http_info(message_id, dm_reaction_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMReactionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->add_dm_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **dm_reaction_request** | [**DMReactionRequest**](DMReactionRequest.md) |  |  |

### Return type

[**DMReactionResponse**](DMReactionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## attach_to_dm_message

> <DMMessageEnvelope> attach_to_dm_message(message_id, dm_attach_request)

Attach a file/image/etc. to an existing DM message.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
dm_attach_request = Spatio::DMAttachRequest.new({kind: 'kind_example', url: 'url_example'}) # DMAttachRequest | 

begin
  # Attach a file/image/etc. to an existing DM message.
  result = api_instance.attach_to_dm_message(message_id, dm_attach_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->attach_to_dm_message: #{e}"
end
```

#### Using the attach_to_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMMessageEnvelope>, Integer, Hash)> attach_to_dm_message_with_http_info(message_id, dm_attach_request)

```ruby
begin
  # Attach a file/image/etc. to an existing DM message.
  data, status_code, headers = api_instance.attach_to_dm_message_with_http_info(message_id, dm_attach_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMMessageEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->attach_to_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **dm_attach_request** | [**DMAttachRequest**](DMAttachRequest.md) |  |  |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## execute_dm_action

> <ExecuteChatActionResponse> execute_dm_action(execute_chat_action_request)

Dispatch a DM action by id.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
execute_chat_action_request = Spatio::ExecuteChatActionRequest.new({action_id: 'action_id_example'}) # ExecuteChatActionRequest | 

begin
  # Dispatch a DM action by id.
  result = api_instance.execute_dm_action(execute_chat_action_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->execute_dm_action: #{e}"
end
```

#### Using the execute_dm_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExecuteChatActionResponse>, Integer, Hash)> execute_dm_action_with_http_info(execute_chat_action_request)

```ruby
begin
  # Dispatch a DM action by id.
  data, status_code, headers = api_instance.execute_dm_action_with_http_info(execute_chat_action_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExecuteChatActionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->execute_dm_action_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **execute_chat_action_request** | [**ExecuteChatActionRequest**](ExecuteChatActionRequest.md) |  |  |

### Return type

[**ExecuteChatActionResponse**](ExecuteChatActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## forward_dm_message

> <DMMessageEnvelope> forward_dm_message(message_id, dm_forward_request)

Forward a DM message to another DM or channel.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
dm_forward_request = Spatio::DMForwardRequest.new # DMForwardRequest | 

begin
  # Forward a DM message to another DM or channel.
  result = api_instance.forward_dm_message(message_id, dm_forward_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->forward_dm_message: #{e}"
end
```

#### Using the forward_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMMessageEnvelope>, Integer, Hash)> forward_dm_message_with_http_info(message_id, dm_forward_request)

```ruby
begin
  # Forward a DM message to another DM or channel.
  data, status_code, headers = api_instance.forward_dm_message_with_http_info(message_id, dm_forward_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMMessageEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->forward_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **dm_forward_request** | [**DMForwardRequest**](DMForwardRequest.md) |  |  |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_dm_user

> <GetChatUserResponse> get_dm_user(id, opts)

Fetch one chat user.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
id = 'id_example' # String | Chat-user id (provider-scoped).
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Fetch one chat user.
  result = api_instance.get_dm_user(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->get_dm_user: #{e}"
end
```

#### Using the get_dm_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetChatUserResponse>, Integer, Hash)> get_dm_user_with_http_info(id, opts)

```ruby
begin
  # Fetch one chat user.
  data, status_code, headers = api_instance.get_dm_user_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetChatUserResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->get_dm_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Chat-user id (provider-scoped). |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**GetChatUserResponse**](GetChatUserResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_direct_conversations_enriched

> Hash&lt;String, Object&gt; list_direct_conversations_enriched(opts)

Enriched DM conversation list with unread + pin + draft state.

Native fast-path. Returns conversations augmented with the DM-feature state (unread counts, pinned/muted flags, saved drafts) the renderer's DM UI consumes. The shape is provider-specific and treated as opaque. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
opts = {
  account_id: 'account_id_example', # String | 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Enriched DM conversation list with unread + pin + draft state.
  result = api_instance.list_direct_conversations_enriched(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_conversations_enriched: #{e}"
end
```

#### Using the list_direct_conversations_enriched_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_direct_conversations_enriched_with_http_info(opts)

```ruby
begin
  # Enriched DM conversation list with unread + pin + draft state.
  data, status_code, headers = api_instance.list_direct_conversations_enriched_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_conversations_enriched_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_direct_message_conversations

> <ListChannelsResponse> list_direct_message_conversations(opts)

List 1:1 and group DM conversations.

Returns DM-type conversations only (`type: im | mpim`). Channel-type conversations are surfaced via `/v1/channels`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  cursor: 'cursor_example', # String | 
  include_archived: true # Boolean | 
}

begin
  # List 1:1 and group DM conversations.
  result = api_instance.list_direct_message_conversations(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_message_conversations: #{e}"
end
```

#### Using the list_direct_message_conversations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListChannelsResponse>, Integer, Hash)> list_direct_message_conversations_with_http_info(opts)

```ruby
begin
  # List 1:1 and group DM conversations.
  data, status_code, headers = api_instance.list_direct_message_conversations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListChannelsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_message_conversations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** |  | [optional] |
| **include_archived** | **Boolean** |  | [optional][default to false] |

### Return type

[**ListChannelsResponse**](ListChannelsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_direct_messages

> <ListMessagesResponse> list_direct_messages(channel, opts)

List messages in a DM conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
channel = 'channel_example' # String | DM conversation id.
opts = {
  account_id: 'account_id_example', # String | 
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  cursor: 'cursor_example', # String | 
  oldest_first: true # Boolean | 
}

begin
  # List messages in a DM conversation.
  result = api_instance.list_direct_messages(channel, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_messages: #{e}"
end
```

#### Using the list_direct_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMessagesResponse>, Integer, Hash)> list_direct_messages_with_http_info(channel, opts)

```ruby
begin
  # List messages in a DM conversation.
  data, status_code, headers = api_instance.list_direct_messages_with_http_info(channel, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMessagesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_direct_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **channel** | **String** | DM conversation id. |  |
| **account_id** | **String** |  | [optional] |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** |  | [optional] |
| **oldest_first** | **Boolean** |  | [optional] |

### Return type

[**ListMessagesResponse**](ListMessagesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_dm_actions

> <ChatActionsList> list_dm_actions

Discover the action catalog for DirectMessages.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new

begin
  # Discover the action catalog for DirectMessages.
  result = api_instance.list_dm_actions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_actions: #{e}"
end
```

#### Using the list_dm_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ChatActionsList>, Integer, Hash)> list_dm_actions_with_http_info

```ruby
begin
  # Discover the action catalog for DirectMessages.
  data, status_code, headers = api_instance.list_dm_actions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ChatActionsList>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_actions_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ChatActionsList**](ChatActionsList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_dm_pinned_messages

> <DMPinnedList> list_dm_pinned_messages(dm_id, opts)

List pinned messages in a DM conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # List pinned messages in a DM conversation.
  result = api_instance.list_dm_pinned_messages(dm_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_pinned_messages: #{e}"
end
```

#### Using the list_dm_pinned_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMPinnedList>, Integer, Hash)> list_dm_pinned_messages_with_http_info(dm_id, opts)

```ruby
begin
  # List pinned messages in a DM conversation.
  data, status_code, headers = api_instance.list_dm_pinned_messages_with_http_info(dm_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMPinnedList>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_pinned_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**DMPinnedList**](DMPinnedList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_dm_thread_replies

> Hash&lt;String, Object&gt; list_dm_thread_replies(dm_id, message_id, opts)

List replies in a DM message thread.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
message_id = 'message_id_example' # String | Chat-message id.
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # List replies in a DM message thread.
  result = api_instance.list_dm_thread_replies(dm_id, message_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_thread_replies: #{e}"
end
```

#### Using the list_dm_thread_replies_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_dm_thread_replies_with_http_info(dm_id, message_id, opts)

```ruby
begin
  # List replies in a DM message thread.
  data, status_code, headers = api_instance.list_dm_thread_replies_with_http_info(dm_id, message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_thread_replies_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **message_id** | **String** | Chat-message id. |  |
| **account_id** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_dm_users

> <ListChatUsersResponse> list_dm_users(opts)

List chat users (DM contacts) across connected accounts.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  cursor: 'cursor_example' # String | 
}

begin
  # List chat users (DM contacts) across connected accounts.
  result = api_instance.list_dm_users(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_users: #{e}"
end
```

#### Using the list_dm_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListChatUsersResponse>, Integer, Hash)> list_dm_users_with_http_info(opts)

```ruby
begin
  # List chat users (DM contacts) across connected accounts.
  data, status_code, headers = api_instance.list_dm_users_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListChatUsersResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->list_dm_users_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** |  | [optional] |

### Return type

[**ListChatUsersResponse**](ListChatUsersResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_dm_read

> <SuccessFlag> mark_dm_read(dm_id, dm_mark_read_request)

Mark a DM message read.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
dm_mark_read_request = Spatio::DMMarkReadRequest.new({message_id: 'message_id_example'}) # DMMarkReadRequest | 

begin
  # Mark a DM message read.
  result = api_instance.mark_dm_read(dm_id, dm_mark_read_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->mark_dm_read: #{e}"
end
```

#### Using the mark_dm_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> mark_dm_read_with_http_info(dm_id, dm_mark_read_request)

```ruby
begin
  # Mark a DM message read.
  data, status_code, headers = api_instance.mark_dm_read_with_http_info(dm_id, dm_mark_read_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->mark_dm_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **dm_mark_read_request** | [**DMMarkReadRequest**](DMMarkReadRequest.md) |  |  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## mute_dm

> <DMMuteResponse> mute_dm(dm_id, dm_mute_request)

Mute a DM conversation (until a time, or forever).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
dm_mute_request = Spatio::DMMuteRequest.new # DMMuteRequest | 

begin
  # Mute a DM conversation (until a time, or forever).
  result = api_instance.mute_dm(dm_id, dm_mute_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->mute_dm: #{e}"
end
```

#### Using the mute_dm_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMMuteResponse>, Integer, Hash)> mute_dm_with_http_info(dm_id, dm_mute_request)

```ruby
begin
  # Mute a DM conversation (until a time, or forever).
  data, status_code, headers = api_instance.mute_dm_with_http_info(dm_id, dm_mute_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMMuteResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->mute_dm_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **dm_mute_request** | [**DMMuteRequest**](DMMuteRequest.md) |  |  |

### Return type

[**DMMuteResponse**](DMMuteResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## pin_dm_conversation

> <SuccessFlag> pin_dm_conversation(dm_id, opts)

Pin a DM conversation to the top of the sidebar.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Pin a DM conversation to the top of the sidebar.
  result = api_instance.pin_dm_conversation(dm_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->pin_dm_conversation: #{e}"
end
```

#### Using the pin_dm_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> pin_dm_conversation_with_http_info(dm_id, opts)

```ruby
begin
  # Pin a DM conversation to the top of the sidebar.
  data, status_code, headers = api_instance.pin_dm_conversation_with_http_info(dm_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->pin_dm_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## pin_dm_message

> <SuccessFlag> pin_dm_message(message_id, opts)

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

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
opts = {
  channel_membership_request: Spatio::ChannelMembershipRequest.new # ChannelMembershipRequest | 
}

begin
  # Pin a DM message.
  result = api_instance.pin_dm_message(message_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->pin_dm_message: #{e}"
end
```

#### Using the pin_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> pin_dm_message_with_http_info(message_id, opts)

```ruby
begin
  # Pin a DM message.
  data, status_code, headers = api_instance.pin_dm_message_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->pin_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **channel_membership_request** | [**ChannelMembershipRequest**](ChannelMembershipRequest.md) |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## post_dm_thread_reply

> <DMMessageEnvelope> post_dm_thread_reply(dm_id, message_id, dm_thread_reply_request, opts)

Reply in a DM message thread.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
message_id = 'message_id_example' # String | Chat-message id.
dm_thread_reply_request = Spatio::DMThreadReplyRequest.new({content: 'content_example'}) # DMThreadReplyRequest | 
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Reply in a DM message thread.
  result = api_instance.post_dm_thread_reply(dm_id, message_id, dm_thread_reply_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->post_dm_thread_reply: #{e}"
end
```

#### Using the post_dm_thread_reply_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMMessageEnvelope>, Integer, Hash)> post_dm_thread_reply_with_http_info(dm_id, message_id, dm_thread_reply_request, opts)

```ruby
begin
  # Reply in a DM message thread.
  data, status_code, headers = api_instance.post_dm_thread_reply_with_http_info(dm_id, message_id, dm_thread_reply_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMMessageEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->post_dm_thread_reply_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **message_id** | **String** | Chat-message id. |  |
| **dm_thread_reply_request** | [**DMThreadReplyRequest**](DMThreadReplyRequest.md) |  |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**DMMessageEnvelope**](DMMessageEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_dm_reaction

> <DMReactionResponse> remove_dm_reaction(message_id, emoji, opts)

Remove a DM message reaction.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
emoji = 'emoji_example' # String | Reaction emoji (e.g. `+1`, `eyes`, `pepper`).
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Remove a DM message reaction.
  result = api_instance.remove_dm_reaction(message_id, emoji, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->remove_dm_reaction: #{e}"
end
```

#### Using the remove_dm_reaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMReactionResponse>, Integer, Hash)> remove_dm_reaction_with_http_info(message_id, emoji, opts)

```ruby
begin
  # Remove a DM message reaction.
  data, status_code, headers = api_instance.remove_dm_reaction_with_http_info(message_id, emoji, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMReactionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->remove_dm_reaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **emoji** | **String** | Reaction emoji (e.g. &#x60;+1&#x60;, &#x60;eyes&#x60;, &#x60;pepper&#x60;). |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**DMReactionResponse**](DMReactionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## search_direct_messages

> <DMSearchResults> search_direct_messages(q, opts)

Search across DM messages.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
q = 'q_example' # String | Free-form query string.
opts = {
  limit: 56, # Integer | 
  dm_id: 'dm_id_example', # String | Restrict to one conversation.
  user: 'user_example', # String | Restrict to messages from this user id.
  account_id: 'account_id_example' # String | 
}

begin
  # Search across DM messages.
  result = api_instance.search_direct_messages(q, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->search_direct_messages: #{e}"
end
```

#### Using the search_direct_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DMSearchResults>, Integer, Hash)> search_direct_messages_with_http_info(q, opts)

```ruby
begin
  # Search across DM messages.
  data, status_code, headers = api_instance.search_direct_messages_with_http_info(q, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DMSearchResults>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->search_direct_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **q** | **String** | Free-form query string. |  |
| **limit** | **Integer** |  | [optional] |
| **dm_id** | **String** | Restrict to one conversation. | [optional] |
| **user** | **String** | Restrict to messages from this user id. | [optional] |
| **account_id** | **String** |  | [optional] |

### Return type

[**DMSearchResults**](DMSearchResults.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_direct_message

> <SendChatMessageResponse> send_direct_message(send_chat_message_request)

Send a DM.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
send_chat_message_request = Spatio::SendChatMessageRequest.new({channel: 'channel_example', text: 'text_example'}) # SendChatMessageRequest | 

begin
  # Send a DM.
  result = api_instance.send_direct_message(send_chat_message_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->send_direct_message: #{e}"
end
```

#### Using the send_direct_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendChatMessageResponse>, Integer, Hash)> send_direct_message_with_http_info(send_chat_message_request)

```ruby
begin
  # Send a DM.
  data, status_code, headers = api_instance.send_direct_message_with_http_info(send_chat_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendChatMessageResponse>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->send_direct_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **send_chat_message_request** | [**SendChatMessageRequest**](SendChatMessageRequest.md) |  |  |

### Return type

[**SendChatMessageResponse**](SendChatMessageResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## set_dm_draft

> <SuccessFlag> set_dm_draft(dm_id, dm_set_draft_request)

Save the unsent draft text for a DM.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
dm_set_draft_request = Spatio::DMSetDraftRequest.new({text: 'text_example'}) # DMSetDraftRequest | 

begin
  # Save the unsent draft text for a DM.
  result = api_instance.set_dm_draft(dm_id, dm_set_draft_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->set_dm_draft: #{e}"
end
```

#### Using the set_dm_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> set_dm_draft_with_http_info(dm_id, dm_set_draft_request)

```ruby
begin
  # Save the unsent draft text for a DM.
  data, status_code, headers = api_instance.set_dm_draft_with_http_info(dm_id, dm_set_draft_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->set_dm_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **dm_set_draft_request** | [**DMSetDraftRequest**](DMSetDraftRequest.md) |  |  |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## unpin_dm_conversation

> <SuccessFlag> unpin_dm_conversation(dm_id, opts)

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

api_instance = Spatio::DirectMessagesApi.new
dm_id = 'dm_id_example' # String | Direct-message conversation id.
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Unpin a DM conversation.
  result = api_instance.unpin_dm_conversation(dm_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->unpin_dm_conversation: #{e}"
end
```

#### Using the unpin_dm_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> unpin_dm_conversation_with_http_info(dm_id, opts)

```ruby
begin
  # Unpin a DM conversation.
  data, status_code, headers = api_instance.unpin_dm_conversation_with_http_info(dm_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->unpin_dm_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dm_id** | **String** | Direct-message conversation id. |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## unpin_dm_message

> <SuccessFlag> unpin_dm_message(message_id, opts)

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

api_instance = Spatio::DirectMessagesApi.new
message_id = 'message_id_example' # String | Chat-message id.
opts = {
  account_id: 'account_id_example' # String | 
}

begin
  # Unpin a DM message.
  result = api_instance.unpin_dm_message(message_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->unpin_dm_message: #{e}"
end
```

#### Using the unpin_dm_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> unpin_dm_message_with_http_info(message_id, opts)

```ruby
begin
  # Unpin a DM message.
  data, status_code, headers = api_instance.unpin_dm_message_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->unpin_dm_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Chat-message id. |  |
| **account_id** | **String** |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_execute_dm_action

> Hash&lt;String, Object&gt; workspace_execute_dm_action(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_execute_dm_action(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_execute_dm_action: #{e}"
end
```

#### Using the workspace_execute_dm_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_execute_dm_action_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_execute_dm_action_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_execute_dm_action_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_get_dm_user

> Hash&lt;String, Object&gt; workspace_get_dm_user(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_dm_user(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_get_dm_user: #{e}"
end
```

#### Using the workspace_get_dm_user_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_dm_user_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_dm_user_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_get_dm_user_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_direct_messages

> Hash&lt;String, Object&gt; workspace_list_direct_messages(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_direct_messages(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_direct_messages: #{e}"
end
```

#### Using the workspace_list_direct_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_direct_messages_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_direct_messages_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_direct_messages_with_http_info: #{e}"
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


## workspace_list_dm_actions

> Hash&lt;String, Object&gt; workspace_list_dm_actions(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_dm_actions(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_actions: #{e}"
end
```

#### Using the workspace_list_dm_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_dm_actions_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_dm_actions_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_actions_with_http_info: #{e}"
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


## workspace_list_dm_conversations

> Hash&lt;String, Object&gt; workspace_list_dm_conversations(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_dm_conversations(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_conversations: #{e}"
end
```

#### Using the workspace_list_dm_conversations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_dm_conversations_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_dm_conversations_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_conversations_with_http_info: #{e}"
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


## workspace_list_dm_messages

> Hash&lt;String, Object&gt; workspace_list_dm_messages(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_dm_messages(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_messages: #{e}"
end
```

#### Using the workspace_list_dm_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_dm_messages_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_dm_messages_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_messages_with_http_info: #{e}"
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


## workspace_list_dm_users

> Hash&lt;String, Object&gt; workspace_list_dm_users(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_dm_users(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_users: #{e}"
end
```

#### Using the workspace_list_dm_users_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_dm_users_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_dm_users_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_list_dm_users_with_http_info: #{e}"
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


## workspace_send_direct_message

> Hash&lt;String, Object&gt; workspace_send_direct_message(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::DirectMessagesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_send_direct_message(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_send_direct_message: #{e}"
end
```

#### Using the workspace_send_direct_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_send_direct_message_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_send_direct_message_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling DirectMessagesApi->workspace_send_direct_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

