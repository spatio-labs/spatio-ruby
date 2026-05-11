# Spatio::ChannelsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_channel**](ChannelsApi.md#create_channel) | **POST** /v1/channels | Create a channel. |
| [**execute_channel_action**](ChannelsApi.md#execute_channel_action) | **POST** /v1/channels/execute | Dispatch a channel action by id. |
| [**join_channel**](ChannelsApi.md#join_channel) | **POST** /v1/channels/{id}/join | Join a channel. |
| [**leave_channel**](ChannelsApi.md#leave_channel) | **POST** /v1/channels/{id}/leave | Leave a channel. |
| [**list_channel_actions**](ChannelsApi.md#list_channel_actions) | **GET** /v1/channels/actions | Discover the action catalog for the Channels platform. |
| [**list_channel_messages**](ChannelsApi.md#list_channel_messages) | **GET** /v1/channels/messages | List messages in a channel. |
| [**list_channels**](ChannelsApi.md#list_channels) | **GET** /v1/channels | List group channels across connected chat providers. |
| [**send_channel_message**](ChannelsApi.md#send_channel_message) | **POST** /v1/channels/messages | Send a message to a channel. |
| [**workspace_create_channel**](ChannelsApi.md#workspace_create_channel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspace_execute_channel_action**](ChannelsApi.md#workspace_execute_channel_action) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/execute |  |
| [**workspace_join_channel**](ChannelsApi.md#workspace_join_channel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/join |  |
| [**workspace_leave_channel**](ChannelsApi.md#workspace_leave_channel) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/{id}/leave |  |
| [**workspace_list_channel_actions**](ChannelsApi.md#workspace_list_channel_actions) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/actions |  |
| [**workspace_list_channel_messages**](ChannelsApi.md#workspace_list_channel_messages) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |
| [**workspace_list_channels**](ChannelsApi.md#workspace_list_channels) | **GET** /v1/organizations/{org}/workspaces/{workspace}/channels |  |
| [**workspace_send_channel_message**](ChannelsApi.md#workspace_send_channel_message) | **POST** /v1/organizations/{org}/workspaces/{workspace}/channels/messages |  |


## create_channel

> <CreateChannelResponse> create_channel(create_channel_request)

Create a channel.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
create_channel_request = Spatio::CreateChannelRequest.new({name: 'name_example'}) # CreateChannelRequest | 

begin
  # Create a channel.
  result = api_instance.create_channel(create_channel_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->create_channel: #{e}"
end
```

#### Using the create_channel_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateChannelResponse>, Integer, Hash)> create_channel_with_http_info(create_channel_request)

```ruby
begin
  # Create a channel.
  data, status_code, headers = api_instance.create_channel_with_http_info(create_channel_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateChannelResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->create_channel_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_channel_request** | [**CreateChannelRequest**](CreateChannelRequest.md) |  |  |

### Return type

[**CreateChannelResponse**](CreateChannelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## execute_channel_action

> <ExecuteChatActionResponse> execute_channel_action(execute_chat_action_request)

Dispatch a channel action by id.

Generic action-execution endpoint. `params` shape varies per `action_id`; consult `GET /v1/channels/actions` for the per-id contract. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
execute_chat_action_request = Spatio::ExecuteChatActionRequest.new({action_id: 'action_id_example'}) # ExecuteChatActionRequest | 

begin
  # Dispatch a channel action by id.
  result = api_instance.execute_channel_action(execute_chat_action_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->execute_channel_action: #{e}"
end
```

#### Using the execute_channel_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExecuteChatActionResponse>, Integer, Hash)> execute_channel_action_with_http_info(execute_chat_action_request)

```ruby
begin
  # Dispatch a channel action by id.
  data, status_code, headers = api_instance.execute_channel_action_with_http_info(execute_chat_action_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExecuteChatActionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->execute_channel_action_with_http_info: #{e}"
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


## join_channel

> <SuccessFlag> join_channel(id, opts)

Join a channel.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
id = 'id_example' # String | Channel id (provider-scoped).
opts = {
  channel_membership_request: Spatio::ChannelMembershipRequest.new # ChannelMembershipRequest | 
}

begin
  # Join a channel.
  result = api_instance.join_channel(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->join_channel: #{e}"
end
```

#### Using the join_channel_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> join_channel_with_http_info(id, opts)

```ruby
begin
  # Join a channel.
  data, status_code, headers = api_instance.join_channel_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->join_channel_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Channel id (provider-scoped). |  |
| **channel_membership_request** | [**ChannelMembershipRequest**](ChannelMembershipRequest.md) |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## leave_channel

> <SuccessFlag> leave_channel(id, opts)

Leave a channel.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
id = 'id_example' # String | Channel id (provider-scoped).
opts = {
  channel_membership_request: Spatio::ChannelMembershipRequest.new # ChannelMembershipRequest | 
}

begin
  # Leave a channel.
  result = api_instance.leave_channel(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->leave_channel: #{e}"
end
```

#### Using the leave_channel_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> leave_channel_with_http_info(id, opts)

```ruby
begin
  # Leave a channel.
  data, status_code, headers = api_instance.leave_channel_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->leave_channel_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Channel id (provider-scoped). |  |
| **channel_membership_request** | [**ChannelMembershipRequest**](ChannelMembershipRequest.md) |  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_channel_actions

> <ChatActionsList> list_channel_actions

Discover the action catalog for the Channels platform.

Returns the action descriptors the agent layer dispatches via `POST /v1/channels/execute`. Same pattern as the DirectMessages action surface. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new

begin
  # Discover the action catalog for the Channels platform.
  result = api_instance.list_channel_actions
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channel_actions: #{e}"
end
```

#### Using the list_channel_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ChatActionsList>, Integer, Hash)> list_channel_actions_with_http_info

```ruby
begin
  # Discover the action catalog for the Channels platform.
  data, status_code, headers = api_instance.list_channel_actions_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ChatActionsList>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channel_actions_with_http_info: #{e}"
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


## list_channel_messages

> <ListMessagesResponse> list_channel_messages(channel, opts)

List messages in a channel.

Channel ids are provider-scoped; pass `?accountId=` (preferred) or `?accountIds=` to disambiguate when the same id exists on multiple connected accounts (rare). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
channel = 'channel_example' # String | Channel id.
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
  # List messages in a channel.
  result = api_instance.list_channel_messages(channel, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channel_messages: #{e}"
end
```

#### Using the list_channel_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListMessagesResponse>, Integer, Hash)> list_channel_messages_with_http_info(channel, opts)

```ruby
begin
  # List messages in a channel.
  data, status_code, headers = api_instance.list_channel_messages_with_http_info(channel, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListMessagesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channel_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **channel** | **String** | Channel id. |  |
| **account_id** | **String** |  | [optional] |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** |  | [optional] |
| **oldest_first** | **Boolean** |  | [optional][default to false] |

### Return type

[**ListMessagesResponse**](ListMessagesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_channels

> <ListChannelsResponse> list_channels(opts)

List group channels across connected chat providers.

Fan-out list. The Channels surface filters to channel-type conversations only (`type: channel | private`); for direct messages use `/v1/direct-messages`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  cursor: 'cursor_example', # String | Provider-specific pagination cursor.
  include_archived: true, # Boolean | 
  types: ['inner_example'] # Array<String> | Repeatable filter on `Channel.type`. Defaults applied by the platform exclude DMs; passing this overrides. 
}

begin
  # List group channels across connected chat providers.
  result = api_instance.list_channels(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channels: #{e}"
end
```

#### Using the list_channels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListChannelsResponse>, Integer, Hash)> list_channels_with_http_info(opts)

```ruby
begin
  # List group channels across connected chat providers.
  data, status_code, headers = api_instance.list_channels_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListChannelsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->list_channels_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** | Provider-specific pagination cursor. | [optional] |
| **include_archived** | **Boolean** |  | [optional][default to false] |
| **types** | [**Array&lt;String&gt;**](String.md) | Repeatable filter on &#x60;Channel.type&#x60;. Defaults applied by the platform exclude DMs; passing this overrides.  | [optional] |

### Return type

[**ListChannelsResponse**](ListChannelsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_channel_message

> <SendChatMessageResponse> send_channel_message(send_chat_message_request)

Send a message to a channel.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
send_chat_message_request = Spatio::SendChatMessageRequest.new({channel: 'channel_example', text: 'text_example'}) # SendChatMessageRequest | 

begin
  # Send a message to a channel.
  result = api_instance.send_channel_message(send_chat_message_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->send_channel_message: #{e}"
end
```

#### Using the send_channel_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendChatMessageResponse>, Integer, Hash)> send_channel_message_with_http_info(send_chat_message_request)

```ruby
begin
  # Send a message to a channel.
  data, status_code, headers = api_instance.send_channel_message_with_http_info(send_chat_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendChatMessageResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->send_channel_message_with_http_info: #{e}"
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


## workspace_create_channel

> Hash&lt;String, Object&gt; workspace_create_channel(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_channel(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_create_channel: #{e}"
end
```

#### Using the workspace_create_channel_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_channel_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_channel_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_create_channel_with_http_info: #{e}"
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


## workspace_execute_channel_action

> Hash&lt;String, Object&gt; workspace_execute_channel_action(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_execute_channel_action(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_execute_channel_action: #{e}"
end
```

#### Using the workspace_execute_channel_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_execute_channel_action_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_execute_channel_action_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_execute_channel_action_with_http_info: #{e}"
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


## workspace_join_channel

> workspace_join_channel(org, workspace, id, opts)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  
  api_instance.workspace_join_channel(org, workspace, id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_join_channel: #{e}"
end
```

#### Using the workspace_join_channel_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_join_channel_with_http_info(org, workspace, id, opts)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_join_channel_with_http_info(org, workspace, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_join_channel_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_leave_channel

> workspace_leave_channel(org, workspace, id, opts)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  
  api_instance.workspace_leave_channel(org, workspace, id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_leave_channel: #{e}"
end
```

#### Using the workspace_leave_channel_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_leave_channel_with_http_info(org, workspace, id, opts)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_leave_channel_with_http_info(org, workspace, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_leave_channel_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_list_channel_actions

> Hash&lt;String, Object&gt; workspace_list_channel_actions(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_channel_actions(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channel_actions: #{e}"
end
```

#### Using the workspace_list_channel_actions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_channel_actions_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_channel_actions_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channel_actions_with_http_info: #{e}"
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


## workspace_list_channel_messages

> Hash&lt;String, Object&gt; workspace_list_channel_messages(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_channel_messages(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channel_messages: #{e}"
end
```

#### Using the workspace_list_channel_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_channel_messages_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_channel_messages_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channel_messages_with_http_info: #{e}"
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


## workspace_list_channels

> Hash&lt;String, Object&gt; workspace_list_channels(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_channels(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channels: #{e}"
end
```

#### Using the workspace_list_channels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_channels_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_channels_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_list_channels_with_http_info: #{e}"
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


## workspace_send_channel_message

> Hash&lt;String, Object&gt; workspace_send_channel_message(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ChannelsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_send_channel_message(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_send_channel_message: #{e}"
end
```

#### Using the workspace_send_channel_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_send_channel_message_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_send_channel_message_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling ChannelsApi->workspace_send_channel_message_with_http_info: #{e}"
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

