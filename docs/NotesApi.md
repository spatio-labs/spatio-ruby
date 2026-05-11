# Spatio::NotesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_block**](NotesApi.md#create_block) | **POST** /v1/notes/{id}/blocks | Insert a block in a note. |
| [**create_note**](NotesApi.md#create_note) | **POST** /v1/notes | Create a note. |
| [**create_note_comment**](NotesApi.md#create_note_comment) | **POST** /v1/notes/{id}/comments | Create a comment or reply. |
| [**delete_block**](NotesApi.md#delete_block) | **DELETE** /v1/notes/blocks/{id} | Delete a block. |
| [**delete_note**](NotesApi.md#delete_note) | **DELETE** /v1/notes/{id} | Delete a note. |
| [**delete_note_comment**](NotesApi.md#delete_note_comment) | **DELETE** /v1/notes/{id}/comments/{commentId} | Soft-delete (native) or hard-delete (provider) a comment. |
| [**disable_note_share**](NotesApi.md#disable_note_share) | **DELETE** /v1/notes/{id}/share | Disable public sharing. |
| [**enable_note_share**](NotesApi.md#enable_note_share) | **POST** /v1/notes/{id}/share | Enable (or update password on) public sharing. |
| [**get_block**](NotesApi.md#get_block) | **GET** /v1/notes/blocks/{id} | Fetch one block. |
| [**get_note**](NotesApi.md#get_note) | **GET** /v1/notes/{id} | Fetch one note. |
| [**get_note_comment**](NotesApi.md#get_note_comment) | **GET** /v1/notes/{id}/comments/{commentId} | Fetch one comment. |
| [**get_note_share_settings**](NotesApi.md#get_note_share_settings) | **GET** /v1/notes/{id}/share | Fetch share settings for a note. |
| [**get_public_note**](NotesApi.md#get_public_note) | **GET** /public/notes/{token} | Fetch a publicly shared note. |
| [**list_blocks**](NotesApi.md#list_blocks) | **GET** /v1/notes/{id}/blocks | List blocks under a note. |
| [**list_note_comments**](NotesApi.md#list_note_comments) | **GET** /v1/notes/{id}/comments | List comments on a note. |
| [**list_notes**](NotesApi.md#list_notes) | **GET** /v1/notes | List notes across connected accounts. |
| [**move_block**](NotesApi.md#move_block) | **POST** /v1/notes/blocks/{id}/move | Reparent or reorder a block. |
| [**rotate_note_share_token**](NotesApi.md#rotate_note_share_token) | **POST** /v1/notes/{id}/share/rotate | Rotate the share token, invalidating any outstanding URLs. |
| [**update_block**](NotesApi.md#update_block) | **PATCH** /v1/notes/blocks/{id} | Update a block (partial). |
| [**update_note**](NotesApi.md#update_note) | **PATCH** /v1/notes/{id} | Update a note (partial). |
| [**update_note_comment**](NotesApi.md#update_note_comment) | **PATCH** /v1/notes/{id}/comments/{commentId} | Edit a comment. |
| [**workspace_create_note**](NotesApi.md#workspace_create_note) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**workspace_create_note_block**](NotesApi.md#workspace_create_note_block) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**workspace_delete_note**](NotesApi.md#workspace_delete_note) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspace_delete_note_block**](NotesApi.md#workspace_delete_note_block) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**workspace_get_note**](NotesApi.md#workspace_get_note) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspace_get_note_block**](NotesApi.md#workspace_get_note_block) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |
| [**workspace_list_note_blocks**](NotesApi.md#workspace_list_note_blocks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes/{id}/blocks |  |
| [**workspace_list_notes**](NotesApi.md#workspace_list_notes) | **GET** /v1/organizations/{org}/workspaces/{workspace}/notes |  |
| [**workspace_move_note_block**](NotesApi.md#workspace_move_note_block) | **POST** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id}/move |  |
| [**workspace_update_note**](NotesApi.md#workspace_update_note) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/{id} |  |
| [**workspace_update_note_block**](NotesApi.md#workspace_update_note_block) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/notes/blocks/{id} |  |


## create_block

> <Block> create_block(id, create_block_request, opts)

Insert a block in a note.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
create_block_request = Spatio::CreateBlockRequest.new({type: Spatio::BlockType::PARAGRAPH, content: Spatio::BlockContent.new, position: 37}) # CreateBlockRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Insert a block in a note.
  result = api_instance.create_block(id, create_block_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_block: #{e}"
end
```

#### Using the create_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Block>, Integer, Hash)> create_block_with_http_info(id, create_block_request, opts)

```ruby
begin
  # Insert a block in a note.
  data, status_code, headers = api_instance.create_block_with_http_info(id, create_block_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Block>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **create_block_request** | [**CreateBlockRequest**](CreateBlockRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_note

> <Note> create_note(create_note_request, opts)

Create a note.

Creates a new note under the target account. The target is resolved in this order: `accountId` field on the body → `?accountId=` query → `provider` field on the body → `?provider=` query → the caller's single connected account (errors with `ambiguous_account` if more than one is connected and no selector is supplied). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
create_note_request = Spatio::CreateNoteRequest.new({title: 'title_example'}) # CreateNoteRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a note.
  result = api_instance.create_note(create_note_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_note: #{e}"
end
```

#### Using the create_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Note>, Integer, Hash)> create_note_with_http_info(create_note_request, opts)

```ruby
begin
  # Create a note.
  data, status_code, headers = api_instance.create_note_with_http_info(create_note_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Note>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_note_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_note_request** | [**CreateNoteRequest**](CreateNoteRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_note_comment

> <CommentMutationResponse> create_note_comment(id, create_comment_request, opts)

Create a comment or reply.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
create_comment_request = Spatio::CreateCommentRequest.new # CreateCommentRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a comment or reply.
  result = api_instance.create_note_comment(id, create_comment_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_note_comment: #{e}"
end
```

#### Using the create_note_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CommentMutationResponse>, Integer, Hash)> create_note_comment_with_http_info(id, create_comment_request, opts)

```ruby
begin
  # Create a comment or reply.
  data, status_code, headers = api_instance.create_note_comment_with_http_info(id, create_comment_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CommentMutationResponse>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->create_note_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **create_comment_request** | [**CreateCommentRequest**](CreateCommentRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CommentMutationResponse**](CommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_block

> <SuccessFlag> delete_block(id, opts)

Delete a block.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Block id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a block.
  result = api_instance.delete_block(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_block: #{e}"
end
```

#### Using the delete_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_block_with_http_info(id, opts)

```ruby
begin
  # Delete a block.
  data, status_code, headers = api_instance.delete_block_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Block id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_note

> <SuccessFlag> delete_note(id, opts)

Delete a note.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a note.
  result = api_instance.delete_note(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_note: #{e}"
end
```

#### Using the delete_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_note_with_http_info(id, opts)

```ruby
begin
  # Delete a note.
  data, status_code, headers = api_instance.delete_note_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_note_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_note_comment

> <SuccessFlag> delete_note_comment(id, comment_id, opts)

Soft-delete (native) or hard-delete (provider) a comment.

Allowed for the comment author and for the note owner. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
comment_id = 'comment_id_example' # String | Comment id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Soft-delete (native) or hard-delete (provider) a comment.
  result = api_instance.delete_note_comment(id, comment_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_note_comment: #{e}"
end
```

#### Using the delete_note_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_note_comment_with_http_info(id, comment_id, opts)

```ruby
begin
  # Soft-delete (native) or hard-delete (provider) a comment.
  data, status_code, headers = api_instance.delete_note_comment_with_http_info(id, comment_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->delete_note_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
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


## disable_note_share

> disable_note_share(id, opts)

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Disable public sharing.
  api_instance.disable_note_share(id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->disable_note_share: #{e}"
end
```

#### Using the disable_note_share_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> disable_note_share_with_http_info(id, opts)

```ruby
begin
  # Disable public sharing.
  data, status_code, headers = api_instance.disable_note_share_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->disable_note_share_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## enable_note_share

> <ShareSettings> enable_note_share(id, opts)

Enable (or update password on) public sharing.

Owner-only. Calling with an empty body or `setPassword: false` flips the note public without changing the password. With `setPassword: true`, applies `password` (empty string clears). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  enable_share_request: Spatio::EnableShareRequest.new # EnableShareRequest | 
}

begin
  # Enable (or update password on) public sharing.
  result = api_instance.enable_note_share(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->enable_note_share: #{e}"
end
```

#### Using the enable_note_share_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> enable_note_share_with_http_info(id, opts)

```ruby
begin
  # Enable (or update password on) public sharing.
  data, status_code, headers = api_instance.enable_note_share_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->enable_note_share_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **enable_share_request** | [**EnableShareRequest**](EnableShareRequest.md) |  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_block

> <Block> get_block(id, opts)

Fetch one block.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Block id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one block.
  result = api_instance.get_block(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_block: #{e}"
end
```

#### Using the get_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Block>, Integer, Hash)> get_block_with_http_info(id, opts)

```ruby
begin
  # Fetch one block.
  data, status_code, headers = api_instance.get_block_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Block>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Block id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_note

> <Note> get_note(id, opts)

Fetch one note.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one note.
  result = api_instance.get_note(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note: #{e}"
end
```

#### Using the get_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Note>, Integer, Hash)> get_note_with_http_info(id, opts)

```ruby
begin
  # Fetch one note.
  data, status_code, headers = api_instance.get_note_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Note>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_note_comment

> <CommentResponse> get_note_comment(id, comment_id, opts)

Fetch one comment.

Useful for permalink hydration when the renderer deep-links into a reply thread. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
comment_id = 'comment_id_example' # String | Comment id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one comment.
  result = api_instance.get_note_comment(id, comment_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note_comment: #{e}"
end
```

#### Using the get_note_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CommentResponse>, Integer, Hash)> get_note_comment_with_http_info(id, comment_id, opts)

```ruby
begin
  # Fetch one comment.
  data, status_code, headers = api_instance.get_note_comment_with_http_info(id, comment_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CommentResponse>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **comment_id** | **String** | Comment id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CommentResponse**](CommentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_note_share_settings

> <ShareSettings> get_note_share_settings(id, opts)

Fetch share settings for a note.

Owner-only. Returns the current public-share configuration, including the share token and computed public viewer URL when the note is currently public. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch share settings for a note.
  result = api_instance.get_note_share_settings(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note_share_settings: #{e}"
end
```

#### Using the get_note_share_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> get_note_share_settings_with_http_info(id, opts)

```ruby
begin
  # Fetch share settings for a note.
  data, status_code, headers = api_instance.get_note_share_settings_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_note_share_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_public_note

> Hash&lt;String, Object&gt; get_public_note(token, opts)

Fetch a publicly shared note.

Unauthenticated. The share token is the credential. For password-protected notes the password is supplied via the `?password=` query param; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt.  Unknown tokens and disabled-share notes both return `404` to prevent token enumeration. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::NotesApi.new
token = 'token_example' # String | Opaque public-share token.
opts = {
  password: 'password_example' # String | Optional viewer password.
}

begin
  # Fetch a publicly shared note.
  result = api_instance.get_public_note(token, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_public_note: #{e}"
end
```

#### Using the get_public_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_public_note_with_http_info(token, opts)

```ruby
begin
  # Fetch a publicly shared note.
  data, status_code, headers = api_instance.get_public_note_with_http_info(token, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->get_public_note_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | Opaque public-share token. |  |
| **password** | **String** | Optional viewer password. | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_blocks

> <BlockListResponse> list_blocks(id, opts)

List blocks under a note.

Returns the block tree for a note, paginated. Block listing always targets a single account (the one that owns the note) so it does not fan out — the response is a plain `{ blocks, total }`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  parent_id: 'parent_id_example', # String | Filter to children of this block id. Omit to list root-level blocks. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List blocks under a note.
  result = api_instance.list_blocks(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_blocks: #{e}"
end
```

#### Using the list_blocks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BlockListResponse>, Integer, Hash)> list_blocks_with_http_info(id, opts)

```ruby
begin
  # List blocks under a note.
  data, status_code, headers = api_instance.list_blocks_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BlockListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_blocks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **parent_id** | **String** | Filter to children of this block id. Omit to list root-level blocks.  | [optional] |
| **limit** | **Integer** |  | [optional][default to 100] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**BlockListResponse**](BlockListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_note_comments

> <CommentListResponse> list_note_comments(id, opts)

List comments on a note.

Returns active (non-deleted) comments. When `?accountId=` targets an external provider that supports comments (e.g. Notion), the provider is queried directly; otherwise the native store is used. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # List comments on a note.
  result = api_instance.list_note_comments(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_note_comments: #{e}"
end
```

#### Using the list_note_comments_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CommentListResponse>, Integer, Hash)> list_note_comments_with_http_info(id, opts)

```ruby
begin
  # List comments on a note.
  data, status_code, headers = api_instance.list_note_comments_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CommentListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_note_comments_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CommentListResponse**](CommentListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_notes

> <NoteListEnvelope> list_notes(opts)

List notes across connected accounts.

Fan-out list. Returns every note visible to the caller across every connected notes provider, paginated by `limit` / `offset`. Pass `?accountId=` or `?provider=` to scope to a single source. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  archived: true, # Boolean | When `true`, return archived notes instead of active ones.
  parent_id: 'parent_id_example', # String | Filter to notes nested under this parent note id.
  tags: ['inner_example'], # Array<String> | Repeatable. Filter to notes carrying every tag listed.
  limit: 56, # Integer | Max items to return. Defaults to 50.
  offset: 56, # Integer | Number of items to skip.
  sort_by: 'sort_by_example', # String | Sort field. Provider-dependent; the native provider supports `updated_at`, `created_at`, `title`. 
  sort_order: 'asc' # String | 
}

begin
  # List notes across connected accounts.
  result = api_instance.list_notes(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_notes: #{e}"
end
```

#### Using the list_notes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<NoteListEnvelope>, Integer, Hash)> list_notes_with_http_info(opts)

```ruby
begin
  # List notes across connected accounts.
  data, status_code, headers = api_instance.list_notes_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <NoteListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->list_notes_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **archived** | **Boolean** | When &#x60;true&#x60;, return archived notes instead of active ones. | [optional][default to false] |
| **parent_id** | **String** | Filter to notes nested under this parent note id. | [optional] |
| **tags** | [**Array&lt;String&gt;**](String.md) | Repeatable. Filter to notes carrying every tag listed. | [optional] |
| **limit** | **Integer** | Max items to return. Defaults to 50. | [optional][default to 50] |
| **offset** | **Integer** | Number of items to skip. | [optional][default to 0] |
| **sort_by** | **String** | Sort field. Provider-dependent; the native provider supports &#x60;updated_at&#x60;, &#x60;created_at&#x60;, &#x60;title&#x60;.  | [optional][default to &#39;updated_at&#39;] |
| **sort_order** | **String** |  | [optional][default to &#39;desc&#39;] |

### Return type

[**NoteListEnvelope**](NoteListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## move_block

> <SuccessFlag> move_block(id, move_block_request, opts)

Reparent or reorder a block.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Block id.
move_block_request = Spatio::MoveBlockRequest.new({position: 37}) # MoveBlockRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Reparent or reorder a block.
  result = api_instance.move_block(id, move_block_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->move_block: #{e}"
end
```

#### Using the move_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> move_block_with_http_info(id, move_block_request, opts)

```ruby
begin
  # Reparent or reorder a block.
  data, status_code, headers = api_instance.move_block_with_http_info(id, move_block_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->move_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Block id. |  |
| **move_block_request** | [**MoveBlockRequest**](MoveBlockRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## rotate_note_share_token

> <ShareSettings> rotate_note_share_token(id, opts)

Rotate the share token, invalidating any outstanding URLs.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Rotate the share token, invalidating any outstanding URLs.
  result = api_instance.rotate_note_share_token(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->rotate_note_share_token: #{e}"
end
```

#### Using the rotate_note_share_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> rotate_note_share_token_with_http_info(id, opts)

```ruby
begin
  # Rotate the share token, invalidating any outstanding URLs.
  data, status_code, headers = api_instance.rotate_note_share_token_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->rotate_note_share_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_block

> <Block> update_block(id, update_block_request, opts)

Update a block (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Block id.
update_block_request = Spatio::UpdateBlockRequest.new # UpdateBlockRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a block (partial).
  result = api_instance.update_block(id, update_block_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_block: #{e}"
end
```

#### Using the update_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Block>, Integer, Hash)> update_block_with_http_info(id, update_block_request, opts)

```ruby
begin
  # Update a block (partial).
  data, status_code, headers = api_instance.update_block_with_http_info(id, update_block_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Block>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Block id. |  |
| **update_block_request** | [**UpdateBlockRequest**](UpdateBlockRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Block**](Block.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_note

> <Note> update_note(id, update_note_request, opts)

Update a note (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
update_note_request = Spatio::UpdateNoteRequest.new # UpdateNoteRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a note (partial).
  result = api_instance.update_note(id, update_note_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_note: #{e}"
end
```

#### Using the update_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Note>, Integer, Hash)> update_note_with_http_info(id, update_note_request, opts)

```ruby
begin
  # Update a note (partial).
  data, status_code, headers = api_instance.update_note_with_http_info(id, update_note_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Note>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_note_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **update_note_request** | [**UpdateNoteRequest**](UpdateNoteRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Note**](Note.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_note_comment

> <CommentMutationResponse> update_note_comment(id, comment_id, update_comment_request, opts)

Edit a comment.

Only the comment author can edit. The note owner can delete via `DELETE` but cannot rewrite. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
id = 'id_example' # String | Note id.
comment_id = 'comment_id_example' # String | Comment id.
update_comment_request = Spatio::UpdateCommentRequest.new # UpdateCommentRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Edit a comment.
  result = api_instance.update_note_comment(id, comment_id, update_comment_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_note_comment: #{e}"
end
```

#### Using the update_note_comment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CommentMutationResponse>, Integer, Hash)> update_note_comment_with_http_info(id, comment_id, update_comment_request, opts)

```ruby
begin
  # Edit a comment.
  data, status_code, headers = api_instance.update_note_comment_with_http_info(id, comment_id, update_comment_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CommentMutationResponse>
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->update_note_comment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Note id. |  |
| **comment_id** | **String** | Comment id. |  |
| **update_comment_request** | [**UpdateCommentRequest**](UpdateCommentRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CommentMutationResponse**](CommentMutationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_note

> Hash&lt;String, Object&gt; workspace_create_note(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_note(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_create_note: #{e}"
end
```

#### Using the workspace_create_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_note_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_note_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_create_note_with_http_info: #{e}"
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


## workspace_create_note_block

> Hash&lt;String, Object&gt; workspace_create_note_block(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_note_block(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_create_note_block: #{e}"
end
```

#### Using the workspace_create_note_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_note_block_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_note_block_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_create_note_block_with_http_info: #{e}"
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


## workspace_delete_note

> workspace_delete_note(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_note(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_delete_note: #{e}"
end
```

#### Using the workspace_delete_note_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_note_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_note_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_delete_note_with_http_info: #{e}"
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


## workspace_delete_note_block

> workspace_delete_note_block(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_note_block(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_delete_note_block: #{e}"
end
```

#### Using the workspace_delete_note_block_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_note_block_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_note_block_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_delete_note_block_with_http_info: #{e}"
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


## workspace_get_note

> Hash&lt;String, Object&gt; workspace_get_note(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_note(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_get_note: #{e}"
end
```

#### Using the workspace_get_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_note_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_note_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_get_note_with_http_info: #{e}"
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


## workspace_get_note_block

> Hash&lt;String, Object&gt; workspace_get_note_block(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_note_block(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_get_note_block: #{e}"
end
```

#### Using the workspace_get_note_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_note_block_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_note_block_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_get_note_block_with_http_info: #{e}"
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


## workspace_list_note_blocks

> Hash&lt;String, Object&gt; workspace_list_note_blocks(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_list_note_blocks(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_list_note_blocks: #{e}"
end
```

#### Using the workspace_list_note_blocks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_note_blocks_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_note_blocks_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_list_note_blocks_with_http_info: #{e}"
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


## workspace_list_notes

> Hash&lt;String, Object&gt; workspace_list_notes(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_notes(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_list_notes: #{e}"
end
```

#### Using the workspace_list_notes_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_notes_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_notes_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_list_notes_with_http_info: #{e}"
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


## workspace_move_note_block

> Hash&lt;String, Object&gt; workspace_move_note_block(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_move_note_block(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_move_note_block: #{e}"
end
```

#### Using the workspace_move_note_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_move_note_block_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_move_note_block_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_move_note_block_with_http_info: #{e}"
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


## workspace_update_note

> Hash&lt;String, Object&gt; workspace_update_note(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_note(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_update_note: #{e}"
end
```

#### Using the workspace_update_note_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_note_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_note_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_update_note_with_http_info: #{e}"
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


## workspace_update_note_block

> Hash&lt;String, Object&gt; workspace_update_note_block(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::NotesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_note_block(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_update_note_block: #{e}"
end
```

#### Using the workspace_update_note_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_note_block_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_note_block_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling NotesApi->workspace_update_note_block_with_http_info: #{e}"
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

