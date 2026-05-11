# Spatio::TasksApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**bulk_delete_tasks**](TasksApi.md#bulk_delete_tasks) | **POST** /v1/tasks/delete | Delete multiple tasks in one call. |
| [**bulk_update_tasks**](TasksApi.md#bulk_update_tasks) | **POST** /v1/tasks/bulk-update | Apply the same update to multiple tasks. |
| [**complete_task**](TasksApi.md#complete_task) | **POST** /v1/tasks/{id}/complete | Mark a task complete. |
| [**create_task**](TasksApi.md#create_task) | **POST** /v1/tasks | Create a task. |
| [**create_task_comment**](TasksApi.md#create_task_comment) | **POST** /v1/tasks/{id}/comments | Create a comment. |
| [**delete_task**](TasksApi.md#delete_task) | **DELETE** /v1/tasks/{id} | Delete a task. |
| [**delete_task_comment**](TasksApi.md#delete_task_comment) | **DELETE** /v1/tasks/{id}/comments/{commentId} | Delete a task comment. |
| [**get_task**](TasksApi.md#get_task) | **GET** /v1/tasks/{id} | Fetch one task. |
| [**list_task_comments**](TasksApi.md#list_task_comments) | **GET** /v1/tasks/{id}/comments | List comments on a task. |
| [**list_task_providers**](TasksApi.md#list_task_providers) | **GET** /v1/tasks/providers | List supported task providers. |
| [**list_tasks**](TasksApi.md#list_tasks) | **GET** /v1/tasks | List tasks across connected accounts. |
| [**update_task**](TasksApi.md#update_task) | **PATCH** /v1/tasks/{id} | Update a task (partial). |
| [**update_task_comment**](TasksApi.md#update_task_comment) | **PATCH** /v1/tasks/{id}/comments/{commentId} | Edit a task comment. |
| [**workspace_complete_task**](TasksApi.md#workspace_complete_task) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id}/complete |  |
| [**workspace_complete_task_alias**](TasksApi.md#workspace_complete_task_alias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/complete/task | Renderer-compat alias for /tasks/{id}/complete. |
| [**workspace_create_task**](TasksApi.md#workspace_create_task) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspace_create_task_alias**](TasksApi.md#workspace_create_task_alias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/tasks/task | Renderer-compat alias for POST /tasks. |
| [**workspace_delete_task**](TasksApi.md#workspace_delete_task) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspace_get_task**](TasksApi.md#workspace_get_task) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspace_list_task_providers**](TasksApi.md#workspace_list_task_providers) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/providers |  |
| [**workspace_list_tasks**](TasksApi.md#workspace_list_tasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks |  |
| [**workspace_list_tasks_alias**](TasksApi.md#workspace_list_tasks_alias) | **GET** /v1/organizations/{org}/workspaces/{workspace}/tasks/tasks | Renderer-compat alias for /tasks. |
| [**workspace_update_task**](TasksApi.md#workspace_update_task) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/tasks/{id} |  |
| [**workspace_update_task_alias**](TasksApi.md#workspace_update_task_alias) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/tasks/task/{id} | Renderer-compat alias for PATCH /tasks/{id}. |


## bulk_delete_tasks

> <BulkDeleteTasksResponse> bulk_delete_tasks(bulk_delete_tasks_request)

Delete multiple tasks in one call.

Replaces the legacy BFF that looped DELETE /v1/tasks/:id. Per-id errors are collected in `failed` rather than failing the whole call — partial success is the norm. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
bulk_delete_tasks_request = Spatio::BulkDeleteTasksRequest.new # BulkDeleteTasksRequest | 

begin
  # Delete multiple tasks in one call.
  result = api_instance.bulk_delete_tasks(bulk_delete_tasks_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->bulk_delete_tasks: #{e}"
end
```

#### Using the bulk_delete_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkDeleteTasksResponse>, Integer, Hash)> bulk_delete_tasks_with_http_info(bulk_delete_tasks_request)

```ruby
begin
  # Delete multiple tasks in one call.
  data, status_code, headers = api_instance.bulk_delete_tasks_with_http_info(bulk_delete_tasks_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkDeleteTasksResponse>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->bulk_delete_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_delete_tasks_request** | [**BulkDeleteTasksRequest**](BulkDeleteTasksRequest.md) |  |  |

### Return type

[**BulkDeleteTasksResponse**](BulkDeleteTasksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## bulk_update_tasks

> <BulkUpdateTasksResponse> bulk_update_tasks(bulk_update_tasks_request)

Apply the same update to multiple tasks.

Same `updates` payload applied to every id in `taskIds`. As with bulk delete, per-id failures collect in `failed`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
bulk_update_tasks_request = Spatio::BulkUpdateTasksRequest.new({task_ids: ['task_ids_example'], updates: Spatio::UpdateTaskRequest.new}) # BulkUpdateTasksRequest | 

begin
  # Apply the same update to multiple tasks.
  result = api_instance.bulk_update_tasks(bulk_update_tasks_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->bulk_update_tasks: #{e}"
end
```

#### Using the bulk_update_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkUpdateTasksResponse>, Integer, Hash)> bulk_update_tasks_with_http_info(bulk_update_tasks_request)

```ruby
begin
  # Apply the same update to multiple tasks.
  data, status_code, headers = api_instance.bulk_update_tasks_with_http_info(bulk_update_tasks_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkUpdateTasksResponse>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->bulk_update_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_update_tasks_request** | [**BulkUpdateTasksRequest**](BulkUpdateTasksRequest.md) |  |  |

### Return type

[**BulkUpdateTasksResponse**](BulkUpdateTasksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## complete_task

> <SuccessFlag> complete_task(id, opts)

Mark a task complete.

Idempotent — completing an already-completed task is a no-op that still returns success. The legacy `POST /v1/tasks/complete/task` endpoint accepts the same operation with the task id in the JSON body instead of the URL; that variant is a renderer-compat shim and is not modeled in the spec. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Mark a task complete.
  result = api_instance.complete_task(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->complete_task: #{e}"
end
```

#### Using the complete_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> complete_task_with_http_info(id, opts)

```ruby
begin
  # Mark a task complete.
  data, status_code, headers = api_instance.complete_task_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->complete_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_task

> <Task> create_task(create_task_request, opts)

Create a task.

Creates a new task under the target account. Target resolution mirrors `POST /v1/notes`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors `ambiguous_account` if more than one and no selector). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
create_task_request = Spatio::CreateTaskRequest.new({title: 'title_example'}) # CreateTaskRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a task.
  result = api_instance.create_task(create_task_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->create_task: #{e}"
end
```

#### Using the create_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Task>, Integer, Hash)> create_task_with_http_info(create_task_request, opts)

```ruby
begin
  # Create a task.
  data, status_code, headers = api_instance.create_task_with_http_info(create_task_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Task>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->create_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_task_request** | [**CreateTaskRequest**](CreateTaskRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_task_comment

> <TaskCommentMutationResponse> create_task_comment(id, task_comment_request, opts)

Create a comment.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
task_comment_request = Spatio::TaskCommentRequest.new({content: 'content_example'}) # TaskCommentRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a comment.
  result = api_instance.create_task_comment(id, task_comment_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->create_task_comment: #{e}"
end
```

#### Using the create_task_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TaskCommentMutationResponse>, Integer, Hash)> create_task_comment_with_http_info(id, task_comment_request, opts)

```ruby
begin
  # Create a comment.
  data, status_code, headers = api_instance.create_task_comment_with_http_info(id, task_comment_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TaskCommentMutationResponse>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->create_task_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **task_comment_request** | [**TaskCommentRequest**](TaskCommentRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**TaskCommentMutationResponse**](TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_task

> <SuccessFlag> delete_task(id, opts)

Delete a task.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a task.
  result = api_instance.delete_task(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->delete_task: #{e}"
end
```

#### Using the delete_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_task_with_http_info(id, opts)

```ruby
begin
  # Delete a task.
  data, status_code, headers = api_instance.delete_task_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->delete_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_task_comment

> <SuccessFlag> delete_task_comment(id, comment_id, opts)

Delete a task comment.

Allowed for the comment author and (for native comments) for the task owner. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
comment_id = 'comment_id_example' # String | Comment id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a task comment.
  result = api_instance.delete_task_comment(id, comment_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->delete_task_comment: #{e}"
end
```

#### Using the delete_task_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_task_comment_with_http_info(id, comment_id, opts)

```ruby
begin
  # Delete a task comment.
  data, status_code, headers = api_instance.delete_task_comment_with_http_info(id, comment_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->delete_task_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **comment_id** | **String** | Comment id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_task

> <Task> get_task(id, opts)

Fetch one task.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one task.
  result = api_instance.get_task(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->get_task: #{e}"
end
```

#### Using the get_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Task>, Integer, Hash)> get_task_with_http_info(id, opts)

```ruby
begin
  # Fetch one task.
  data, status_code, headers = api_instance.get_task_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Task>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->get_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_task_comments

> <TaskCommentList> list_task_comments(id, opts)

List comments on a task.

Returns active comments. When `?accountId=` targets an external provider that supports comments (e.g. Linear), the provider is queried directly; otherwise the native `TaskComment` table is used. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # List comments on a task.
  result = api_instance.list_task_comments(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_task_comments: #{e}"
end
```

#### Using the list_task_comments_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TaskCommentList>, Integer, Hash)> list_task_comments_with_http_info(id, opts)

```ruby
begin
  # List comments on a task.
  data, status_code, headers = api_instance.list_task_comments_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TaskCommentList>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_task_comments_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**TaskCommentList**](TaskCommentList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_task_providers

> <TaskProvidersInfo> list_task_providers

List supported task providers.

Returns the registered task-provider ids and the platform's own metadata. Useful for clients that need to render provider-specific UI (icons, capability flags) before committing to a particular `provider`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new

begin
  # List supported task providers.
  result = api_instance.list_task_providers
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_task_providers: #{e}"
end
```

#### Using the list_task_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TaskProvidersInfo>, Integer, Hash)> list_task_providers_with_http_info

```ruby
begin
  # List supported task providers.
  data, status_code, headers = api_instance.list_task_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TaskProvidersInfo>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_task_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**TaskProvidersInfo**](TaskProvidersInfo.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_tasks

> <TaskListEnvelope> list_tasks(opts)

List tasks across connected accounts.

Fan-out list. Returns every task visible to the caller across every connected tasks provider. Pass `?accountId=` or `?provider=` to scope to a single source. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  completed: true, # Boolean | Include completed tasks. Default `false` (active tasks only). 
  labels: ['inner_example'], # Array<String> | Repeatable. Filter to tasks carrying every label listed.
  parent_task_id: 'parent_task_id_example', # String | Filter to subtasks of this parent.
  type: 'type_example', # String | Discriminator filter (`todo`, `reminder`, `issue`). 
  source_platform: 'source_platform_example', # String | Filter to tasks linked to a given source platform.
  source_id: 'source_id_example', # String | Filter to tasks linked to a specific source artifact id. Pair with `sourcePlatform` for an exact match. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List tasks across connected accounts.
  result = api_instance.list_tasks(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_tasks: #{e}"
end
```

#### Using the list_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TaskListEnvelope>, Integer, Hash)> list_tasks_with_http_info(opts)

```ruby
begin
  # List tasks across connected accounts.
  data, status_code, headers = api_instance.list_tasks_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TaskListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->list_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **completed** | **Boolean** | Include completed tasks. Default &#x60;false&#x60; (active tasks only).  | [optional][default to false] |
| **labels** | [**Array&lt;String&gt;**](String.md) | Repeatable. Filter to tasks carrying every label listed. | [optional] |
| **parent_task_id** | **String** | Filter to subtasks of this parent. | [optional] |
| **type** | **String** | Discriminator filter (&#x60;todo&#x60;, &#x60;reminder&#x60;, &#x60;issue&#x60;).  | [optional] |
| **source_platform** | **String** | Filter to tasks linked to a given source platform. | [optional] |
| **source_id** | **String** | Filter to tasks linked to a specific source artifact id. Pair with &#x60;sourcePlatform&#x60; for an exact match.  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**TaskListEnvelope**](TaskListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_task

> <Task> update_task(id, update_task_request, opts)

Update a task (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
update_task_request = Spatio::UpdateTaskRequest.new # UpdateTaskRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a task (partial).
  result = api_instance.update_task(id, update_task_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->update_task: #{e}"
end
```

#### Using the update_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Task>, Integer, Hash)> update_task_with_http_info(id, update_task_request, opts)

```ruby
begin
  # Update a task (partial).
  data, status_code, headers = api_instance.update_task_with_http_info(id, update_task_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Task>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->update_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **update_task_request** | [**UpdateTaskRequest**](UpdateTaskRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Task**](Task.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_task_comment

> <TaskCommentMutationResponse> update_task_comment(id, comment_id, task_comment_request, opts)

Edit a task comment.

Only the comment author can edit.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
id = 'id_example' # String | Task id.
comment_id = 'comment_id_example' # String | Comment id.
task_comment_request = Spatio::TaskCommentRequest.new({content: 'content_example'}) # TaskCommentRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Edit a task comment.
  result = api_instance.update_task_comment(id, comment_id, task_comment_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->update_task_comment: #{e}"
end
```

#### Using the update_task_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TaskCommentMutationResponse>, Integer, Hash)> update_task_comment_with_http_info(id, comment_id, task_comment_request, opts)

```ruby
begin
  # Edit a task comment.
  data, status_code, headers = api_instance.update_task_comment_with_http_info(id, comment_id, task_comment_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TaskCommentMutationResponse>
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->update_task_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Task id. |  |
| **comment_id** | **String** | Comment id. |  |
| **task_comment_request** | [**TaskCommentRequest**](TaskCommentRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**TaskCommentMutationResponse**](TaskCommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_complete_task

> Hash&lt;String, Object&gt; workspace_complete_task(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_complete_task(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_complete_task: #{e}"
end
```

#### Using the workspace_complete_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_complete_task_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_complete_task_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_complete_task_with_http_info: #{e}"
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


## workspace_complete_task_alias

> Hash&lt;String, Object&gt; workspace_complete_task_alias(org, workspace, request_body)

Renderer-compat alias for /tasks/{id}/complete.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Renderer-compat alias for /tasks/{id}/complete.
  result = api_instance.workspace_complete_task_alias(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_complete_task_alias: #{e}"
end
```

#### Using the workspace_complete_task_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_complete_task_alias_with_http_info(org, workspace, request_body)

```ruby
begin
  # Renderer-compat alias for /tasks/{id}/complete.
  data, status_code, headers = api_instance.workspace_complete_task_alias_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_complete_task_alias_with_http_info: #{e}"
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


## workspace_create_task

> Hash&lt;String, Object&gt; workspace_create_task(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_task(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_create_task: #{e}"
end
```

#### Using the workspace_create_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_task_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_task_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_create_task_with_http_info: #{e}"
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


## workspace_create_task_alias

> Hash&lt;String, Object&gt; workspace_create_task_alias(org, workspace, request_body)

Renderer-compat alias for POST /tasks.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Renderer-compat alias for POST /tasks.
  result = api_instance.workspace_create_task_alias(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_create_task_alias: #{e}"
end
```

#### Using the workspace_create_task_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_task_alias_with_http_info(org, workspace, request_body)

```ruby
begin
  # Renderer-compat alias for POST /tasks.
  data, status_code, headers = api_instance.workspace_create_task_alias_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_create_task_alias_with_http_info: #{e}"
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


## workspace_delete_task

> workspace_delete_task(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_task(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_delete_task: #{e}"
end
```

#### Using the workspace_delete_task_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_task_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_task_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_delete_task_with_http_info: #{e}"
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


## workspace_get_task

> Hash&lt;String, Object&gt; workspace_get_task(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_task(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_get_task: #{e}"
end
```

#### Using the workspace_get_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_task_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_task_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_get_task_with_http_info: #{e}"
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


## workspace_list_task_providers

> Hash&lt;String, Object&gt; workspace_list_task_providers(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_task_providers(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_task_providers: #{e}"
end
```

#### Using the workspace_list_task_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_task_providers_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_task_providers_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_task_providers_with_http_info: #{e}"
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


## workspace_list_tasks

> Hash&lt;String, Object&gt; workspace_list_tasks(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_tasks(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_tasks: #{e}"
end
```

#### Using the workspace_list_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_tasks_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_tasks_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_tasks_with_http_info: #{e}"
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


## workspace_list_tasks_alias

> Hash&lt;String, Object&gt; workspace_list_tasks_alias(org, workspace)

Renderer-compat alias for /tasks.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  # Renderer-compat alias for /tasks.
  result = api_instance.workspace_list_tasks_alias(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_tasks_alias: #{e}"
end
```

#### Using the workspace_list_tasks_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_tasks_alias_with_http_info(org, workspace)

```ruby
begin
  # Renderer-compat alias for /tasks.
  data, status_code, headers = api_instance.workspace_list_tasks_alias_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_list_tasks_alias_with_http_info: #{e}"
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


## workspace_update_task

> Hash&lt;String, Object&gt; workspace_update_task(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_task(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_update_task: #{e}"
end
```

#### Using the workspace_update_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_task_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_task_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_update_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_update_task_alias

> Hash&lt;String, Object&gt; workspace_update_task_alias(org, workspace, id, request_body)

Renderer-compat alias for PATCH /tasks/{id}.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::TasksApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Renderer-compat alias for PATCH /tasks/{id}.
  result = api_instance.workspace_update_task_alias(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_update_task_alias: #{e}"
end
```

#### Using the workspace_update_task_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_task_alias_with_http_info(org, workspace, id, request_body)

```ruby
begin
  # Renderer-compat alias for PATCH /tasks/{id}.
  data, status_code, headers = api_instance.workspace_update_task_alias_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling TasksApi->workspace_update_task_alias_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

