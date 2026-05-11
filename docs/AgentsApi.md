# Spatio::AgentsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_agent**](AgentsApi.md#create_agent) | **POST** /v1/agents | Create a new agent configuration. |
| [**create_agent_conversation**](AgentsApi.md#create_agent_conversation) | **POST** /v1/agent/conversations | Create a new agent-platform conversation. |
| [**create_agent_message**](AgentsApi.md#create_agent_message) | **POST** /v1/agent/conversations/{id}/messages | Append a message to an agent conversation. |
| [**delete_agent**](AgentsApi.md#delete_agent) | **DELETE** /v1/agents/{id} | Delete an agent configuration. |
| [**execute_agent_action**](AgentsApi.md#execute_agent_action) | **POST** /v1/agent/actions/execute | Execute an action through the agent platform. |
| [**get_agent**](AgentsApi.md#get_agent) | **GET** /v1/agents/{id} | Fetch one agent configuration. |
| [**get_agent_conversation**](AgentsApi.md#get_agent_conversation) | **GET** /v1/agent/conversations/{id} | Fetch one agent conversation. |
| [**get_agent_session_context**](AgentsApi.md#get_agent_session_context) | **GET** /v1/agent/session-context | Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn&#39;t fish on its first turn.  |
| [**list_agent_conversation_messages**](AgentsApi.md#list_agent_conversation_messages) | **GET** /v1/agent/conversations/{id}/messages | List messages on an agent conversation. |
| [**list_agent_conversations**](AgentsApi.md#list_agent_conversations) | **GET** /v1/agent/conversations | List the caller&#39;s agent-platform conversations. Distinct from &#x60;/v1/conversations&#x60; (renderer-driven sidebar persistence).  |
| [**list_agents**](AgentsApi.md#list_agents) | **GET** /v1/agents | List the caller&#39;s agent configurations. |
| [**list_preconfigured_agents**](AgentsApi.md#list_preconfigured_agents) | **GET** /v1/agents/preconfigured | Curated featured agents (e.g. \&quot;Claude Code\&quot;, \&quot;Research Assistant\&quot;). Read-only — these are surfaced by the renderer&#39;s preconfigured-picker UI.  |
| [**update_agent**](AgentsApi.md#update_agent) | **PATCH** /v1/agents/{id} | Update an agent configuration. |


## create_agent

> <Agent> create_agent(create_agent_request)

Create a new agent configuration.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
create_agent_request = Spatio::CreateAgentRequest.new({name: 'name_example'}) # CreateAgentRequest | 

begin
  # Create a new agent configuration.
  result = api_instance.create_agent(create_agent_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent: #{e}"
end
```

#### Using the create_agent_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Agent>, Integer, Hash)> create_agent_with_http_info(create_agent_request)

```ruby
begin
  # Create a new agent configuration.
  data, status_code, headers = api_instance.create_agent_with_http_info(create_agent_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Agent>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_agent_request** | [**CreateAgentRequest**](CreateAgentRequest.md) |  |  |

### Return type

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_agent_conversation

> <AgentConversation> create_agent_conversation(opts)

Create a new agent-platform conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
opts = {
  create_agent_conversation_request: Spatio::CreateAgentConversationRequest.new # CreateAgentConversationRequest | 
}

begin
  # Create a new agent-platform conversation.
  result = api_instance.create_agent_conversation(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent_conversation: #{e}"
end
```

#### Using the create_agent_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentConversation>, Integer, Hash)> create_agent_conversation_with_http_info(opts)

```ruby
begin
  # Create a new agent-platform conversation.
  data, status_code, headers = api_instance.create_agent_conversation_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentConversation>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_agent_conversation_request** | [**CreateAgentConversationRequest**](CreateAgentConversationRequest.md) |  | [optional] |

### Return type

[**AgentConversation**](AgentConversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_agent_message

> <AgentMessage> create_agent_message(id, create_agent_message_request)

Append a message to an agent conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 
create_agent_message_request = Spatio::CreateAgentMessageRequest.new({role: 'role_example', content: 'content_example'}) # CreateAgentMessageRequest | 

begin
  # Append a message to an agent conversation.
  result = api_instance.create_agent_message(id, create_agent_message_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent_message: #{e}"
end
```

#### Using the create_agent_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentMessage>, Integer, Hash)> create_agent_message_with_http_info(id, create_agent_message_request)

```ruby
begin
  # Append a message to an agent conversation.
  data, status_code, headers = api_instance.create_agent_message_with_http_info(id, create_agent_message_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentMessage>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->create_agent_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **create_agent_message_request** | [**CreateAgentMessageRequest**](CreateAgentMessageRequest.md) |  |  |

### Return type

[**AgentMessage**](AgentMessage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_agent

> delete_agent(id)

Delete an agent configuration.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 

begin
  # Delete an agent configuration.
  api_instance.delete_agent(id)
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->delete_agent: #{e}"
end
```

#### Using the delete_agent_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_agent_with_http_info(id)

```ruby
begin
  # Delete an agent configuration.
  data, status_code, headers = api_instance.delete_agent_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->delete_agent_with_http_info: #{e}"
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


## execute_agent_action

> <ExecuteActionResponse> execute_agent_action(execute_action_request)

Execute an action through the agent platform.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
execute_action_request = Spatio::ExecuteActionRequest.new({action_id: 'action_id_example'}) # ExecuteActionRequest | 

begin
  # Execute an action through the agent platform.
  result = api_instance.execute_agent_action(execute_action_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->execute_agent_action: #{e}"
end
```

#### Using the execute_agent_action_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExecuteActionResponse>, Integer, Hash)> execute_agent_action_with_http_info(execute_action_request)

```ruby
begin
  # Execute an action through the agent platform.
  data, status_code, headers = api_instance.execute_agent_action_with_http_info(execute_action_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExecuteActionResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->execute_agent_action_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **execute_action_request** | [**ExecuteActionRequest**](ExecuteActionRequest.md) |  |  |

### Return type

[**ExecuteActionResponse**](ExecuteActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_agent

> <Agent> get_agent(id)

Fetch one agent configuration.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 

begin
  # Fetch one agent configuration.
  result = api_instance.get_agent(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent: #{e}"
end
```

#### Using the get_agent_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Agent>, Integer, Hash)> get_agent_with_http_info(id)

```ruby
begin
  # Fetch one agent configuration.
  data, status_code, headers = api_instance.get_agent_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Agent>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_agent_conversation

> <AgentConversation> get_agent_conversation(id)

Fetch one agent conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 

begin
  # Fetch one agent conversation.
  result = api_instance.get_agent_conversation(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent_conversation: #{e}"
end
```

#### Using the get_agent_conversation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentConversation>, Integer, Hash)> get_agent_conversation_with_http_info(id)

```ruby
begin
  # Fetch one agent conversation.
  data, status_code, headers = api_instance.get_agent_conversation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentConversation>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent_conversation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**AgentConversation**](AgentConversation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_agent_session_context

> <AgentSessionContext> get_agent_session_context

Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn't fish on its first turn. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new

begin
  # Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn't fish on its first turn. 
  result = api_instance.get_agent_session_context
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent_session_context: #{e}"
end
```

#### Using the get_agent_session_context_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentSessionContext>, Integer, Hash)> get_agent_session_context_with_http_info

```ruby
begin
  # Identity bundle for the SessionStart hook (user + org + workspace + connected accounts) so the agent doesn't fish on its first turn. 
  data, status_code, headers = api_instance.get_agent_session_context_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentSessionContext>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->get_agent_session_context_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AgentSessionContext**](AgentSessionContext.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_agent_conversation_messages

> <AgentMessageListResponse> list_agent_conversation_messages(id)

List messages on an agent conversation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 

begin
  # List messages on an agent conversation.
  result = api_instance.list_agent_conversation_messages(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agent_conversation_messages: #{e}"
end
```

#### Using the list_agent_conversation_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentMessageListResponse>, Integer, Hash)> list_agent_conversation_messages_with_http_info(id)

```ruby
begin
  # List messages on an agent conversation.
  data, status_code, headers = api_instance.list_agent_conversation_messages_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentMessageListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agent_conversation_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**AgentMessageListResponse**](AgentMessageListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_agent_conversations

> <AgentConversationListResponse> list_agent_conversations

List the caller's agent-platform conversations. Distinct from `/v1/conversations` (renderer-driven sidebar persistence). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new

begin
  # List the caller's agent-platform conversations. Distinct from `/v1/conversations` (renderer-driven sidebar persistence). 
  result = api_instance.list_agent_conversations
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agent_conversations: #{e}"
end
```

#### Using the list_agent_conversations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentConversationListResponse>, Integer, Hash)> list_agent_conversations_with_http_info

```ruby
begin
  # List the caller's agent-platform conversations. Distinct from `/v1/conversations` (renderer-driven sidebar persistence). 
  data, status_code, headers = api_instance.list_agent_conversations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentConversationListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agent_conversations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AgentConversationListResponse**](AgentConversationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_agents

> <AgentListResponse> list_agents

List the caller's agent configurations.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new

begin
  # List the caller's agent configurations.
  result = api_instance.list_agents
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agents: #{e}"
end
```

#### Using the list_agents_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentListResponse>, Integer, Hash)> list_agents_with_http_info

```ruby
begin
  # List the caller's agent configurations.
  data, status_code, headers = api_instance.list_agents_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_agents_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AgentListResponse**](AgentListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_preconfigured_agents

> <Array<PreconfiguredAgent>> list_preconfigured_agents

Curated featured agents (e.g. \"Claude Code\", \"Research Assistant\"). Read-only — these are surfaced by the renderer's preconfigured-picker UI. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new

begin
  # Curated featured agents (e.g. \"Claude Code\", \"Research Assistant\"). Read-only — these are surfaced by the renderer's preconfigured-picker UI. 
  result = api_instance.list_preconfigured_agents
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_preconfigured_agents: #{e}"
end
```

#### Using the list_preconfigured_agents_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Array<PreconfiguredAgent>>, Integer, Hash)> list_preconfigured_agents_with_http_info

```ruby
begin
  # Curated featured agents (e.g. \"Claude Code\", \"Research Assistant\"). Read-only — these are surfaced by the renderer's preconfigured-picker UI. 
  data, status_code, headers = api_instance.list_preconfigured_agents_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Array<PreconfiguredAgent>>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->list_preconfigured_agents_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**Array&lt;PreconfiguredAgent&gt;**](PreconfiguredAgent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_agent

> <Agent> update_agent(id, update_agent_request)

Update an agent configuration.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::AgentsApi.new
id = 'id_example' # String | 
update_agent_request = Spatio::UpdateAgentRequest.new # UpdateAgentRequest | 

begin
  # Update an agent configuration.
  result = api_instance.update_agent(id, update_agent_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->update_agent: #{e}"
end
```

#### Using the update_agent_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Agent>, Integer, Hash)> update_agent_with_http_info(id, update_agent_request)

```ruby
begin
  # Update an agent configuration.
  data, status_code, headers = api_instance.update_agent_with_http_info(id, update_agent_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Agent>
rescue Spatio::ApiError => e
  puts "Error when calling AgentsApi->update_agent_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_agent_request** | [**UpdateAgentRequest**](UpdateAgentRequest.md) |  |  |

### Return type

[**Agent**](Agent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

