# Spatio::WorkspacesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**accept_workspace_invitation**](WorkspacesApi.md#accept_workspace_invitation) | **POST** /v1/invitations/{token}/accept | Accept a workspace invitation by token. The signed-in user&#39;s email must match the invitation. Organization-token accept lives at &#x60;POST /v1/organizations/{org}/accept-invitation&#x60;.  |
| [**add_workspace_member**](WorkspacesApi.md#add_workspace_member) | **POST** /v1/workspaces/{workspaceId}/members | Add a member directly (skips invitation flow). |
| [**create_workspace**](WorkspacesApi.md#create_workspace) | **POST** /v1/workspaces | Create a workspace. Requires &#x60;organizationId&#x60; in the body — bare \&quot;personal\&quot; workspaces aren&#39;t supported on the public API.  |
| [**create_workspace_invitation**](WorkspacesApi.md#create_workspace_invitation) | **POST** /v1/workspaces/{workspaceId}/invitations | Invite a user to a workspace. |
| [**get_public_invitation**](WorkspacesApi.md#get_public_invitation) | **GET** /invitations/{token} | Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in.  |
| [**get_workspace**](WorkspacesApi.md#get_workspace) | **GET** /v1/workspaces/{workspaceId} | Fetch a single workspace by id. |
| [**list_my_workspaces**](WorkspacesApi.md#list_my_workspaces) | **GET** /v1/workspaces | List the caller&#39;s workspaces (across organizations). |
| [**list_workspace_invitations**](WorkspacesApi.md#list_workspace_invitations) | **GET** /v1/workspaces/{workspaceId}/invitations | List pending workspace invitations. |
| [**list_workspace_members**](WorkspacesApi.md#list_workspace_members) | **GET** /v1/workspaces/{workspaceId}/members | List members of a workspace. |
| [**remove_workspace_member**](WorkspacesApi.md#remove_workspace_member) | **DELETE** /v1/workspaces/{workspaceId}/members/{memberId} | Remove a member from the workspace. |
| [**revoke_workspace_invitation**](WorkspacesApi.md#revoke_workspace_invitation) | **DELETE** /v1/workspaces/{workspaceId}/invitations/{invitationId} | Revoke a pending workspace invitation. |
| [**update_workspace**](WorkspacesApi.md#update_workspace) | **PATCH** /v1/workspaces/{workspaceId} | Update workspace metadata. |
| [**update_workspace_member**](WorkspacesApi.md#update_workspace_member) | **PATCH** /v1/workspaces/{workspaceId}/members/{memberId} | Update a member&#39;s role. |


## accept_workspace_invitation

> Hash&lt;String, Object&gt; accept_workspace_invitation(token)

Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
token = 'token_example' # String | 

begin
  # Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 
  result = api_instance.accept_workspace_invitation(token)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->accept_workspace_invitation: #{e}"
end
```

#### Using the accept_workspace_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> accept_workspace_invitation_with_http_info(token)

```ruby
begin
  # Accept a workspace invitation by token. The signed-in user's email must match the invitation. Organization-token accept lives at `POST /v1/organizations/{org}/accept-invitation`. 
  data, status_code, headers = api_instance.accept_workspace_invitation_with_http_info(token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->accept_workspace_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## add_workspace_member

> Hash&lt;String, Object&gt; add_workspace_member(workspace_id, add_workspace_member_request)

Add a member directly (skips invitation flow).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
add_workspace_member_request = Spatio::AddWorkspaceMemberRequest.new({email: 'email_example', role: 'owner'}) # AddWorkspaceMemberRequest | 

begin
  # Add a member directly (skips invitation flow).
  result = api_instance.add_workspace_member(workspace_id, add_workspace_member_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->add_workspace_member: #{e}"
end
```

#### Using the add_workspace_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> add_workspace_member_with_http_info(workspace_id, add_workspace_member_request)

```ruby
begin
  # Add a member directly (skips invitation flow).
  data, status_code, headers = api_instance.add_workspace_member_with_http_info(workspace_id, add_workspace_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->add_workspace_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **add_workspace_member_request** | [**AddWorkspaceMemberRequest**](AddWorkspaceMemberRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_workspace

> <WorkspaceEnvelope> create_workspace(create_workspace_request)

Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
create_workspace_request = Spatio::CreateWorkspaceRequest.new({name: 'name_example'}) # CreateWorkspaceRequest | 

begin
  # Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 
  result = api_instance.create_workspace(create_workspace_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->create_workspace: #{e}"
end
```

#### Using the create_workspace_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceEnvelope>, Integer, Hash)> create_workspace_with_http_info(create_workspace_request)

```ruby
begin
  # Create a workspace. Requires `organizationId` in the body — bare \"personal\" workspaces aren't supported on the public API. 
  data, status_code, headers = api_instance.create_workspace_with_http_info(create_workspace_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->create_workspace_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_workspace_request** | [**CreateWorkspaceRequest**](CreateWorkspaceRequest.md) |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_workspace_invitation

> <WorkspaceInvitation> create_workspace_invitation(workspace_id, create_workspace_invitation_request)

Invite a user to a workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
create_workspace_invitation_request = Spatio::CreateWorkspaceInvitationRequest.new({email: 'email_example', role: 'owner'}) # CreateWorkspaceInvitationRequest | 

begin
  # Invite a user to a workspace.
  result = api_instance.create_workspace_invitation(workspace_id, create_workspace_invitation_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->create_workspace_invitation: #{e}"
end
```

#### Using the create_workspace_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceInvitation>, Integer, Hash)> create_workspace_invitation_with_http_info(workspace_id, create_workspace_invitation_request)

```ruby
begin
  # Invite a user to a workspace.
  data, status_code, headers = api_instance.create_workspace_invitation_with_http_info(workspace_id, create_workspace_invitation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceInvitation>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->create_workspace_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **create_workspace_invitation_request** | [**CreateWorkspaceInvitationRequest**](CreateWorkspaceInvitationRequest.md) |  |  |

### Return type

[**WorkspaceInvitation**](WorkspaceInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_public_invitation

> <PublicInvitationPayload> get_public_invitation(token)

Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
token = 'token_example' # String | 

begin
  # Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 
  result = api_instance.get_public_invitation(token)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->get_public_invitation: #{e}"
end
```

#### Using the get_public_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PublicInvitationPayload>, Integer, Hash)> get_public_invitation_with_http_info(token)

```ruby
begin
  # Fetch invitation details by token (unauthenticated). Used by the renderer to show invitation context before the user signs in. 
  data, status_code, headers = api_instance.get_public_invitation_with_http_info(token)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PublicInvitationPayload>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->get_public_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** |  |  |

### Return type

[**PublicInvitationPayload**](PublicInvitationPayload.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_workspace

> <WorkspaceEnvelope> get_workspace(workspace_id)

Fetch a single workspace by id.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 

begin
  # Fetch a single workspace by id.
  result = api_instance.get_workspace(workspace_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->get_workspace: #{e}"
end
```

#### Using the get_workspace_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceEnvelope>, Integer, Hash)> get_workspace_with_http_info(workspace_id)

```ruby
begin
  # Fetch a single workspace by id.
  data, status_code, headers = api_instance.get_workspace_with_http_info(workspace_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->get_workspace_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_my_workspaces

> <WorkspaceListResponse> list_my_workspaces

List the caller's workspaces (across organizations).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new

begin
  # List the caller's workspaces (across organizations).
  result = api_instance.list_my_workspaces
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_my_workspaces: #{e}"
end
```

#### Using the list_my_workspaces_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceListResponse>, Integer, Hash)> list_my_workspaces_with_http_info

```ruby
begin
  # List the caller's workspaces (across organizations).
  data, status_code, headers = api_instance.list_my_workspaces_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_my_workspaces_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**WorkspaceListResponse**](WorkspaceListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_workspace_invitations

> <WorkspaceInvitationListResponse> list_workspace_invitations(workspace_id)

List pending workspace invitations.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 

begin
  # List pending workspace invitations.
  result = api_instance.list_workspace_invitations(workspace_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_workspace_invitations: #{e}"
end
```

#### Using the list_workspace_invitations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceInvitationListResponse>, Integer, Hash)> list_workspace_invitations_with_http_info(workspace_id)

```ruby
begin
  # List pending workspace invitations.
  data, status_code, headers = api_instance.list_workspace_invitations_with_http_info(workspace_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceInvitationListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_workspace_invitations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |

### Return type

[**WorkspaceInvitationListResponse**](WorkspaceInvitationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_workspace_members

> <WorkspaceMemberListResponse> list_workspace_members(workspace_id)

List members of a workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 

begin
  # List members of a workspace.
  result = api_instance.list_workspace_members(workspace_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_workspace_members: #{e}"
end
```

#### Using the list_workspace_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceMemberListResponse>, Integer, Hash)> list_workspace_members_with_http_info(workspace_id)

```ruby
begin
  # List members of a workspace.
  data, status_code, headers = api_instance.list_workspace_members_with_http_info(workspace_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceMemberListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->list_workspace_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |

### Return type

[**WorkspaceMemberListResponse**](WorkspaceMemberListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_workspace_member

> remove_workspace_member(workspace_id, member_id)

Remove a member from the workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
member_id = 'member_id_example' # String | 

begin
  # Remove a member from the workspace.
  api_instance.remove_workspace_member(workspace_id, member_id)
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->remove_workspace_member: #{e}"
end
```

#### Using the remove_workspace_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_workspace_member_with_http_info(workspace_id, member_id)

```ruby
begin
  # Remove a member from the workspace.
  data, status_code, headers = api_instance.remove_workspace_member_with_http_info(workspace_id, member_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->remove_workspace_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **member_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_workspace_invitation

> revoke_workspace_invitation(workspace_id, invitation_id)

Revoke a pending workspace invitation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
invitation_id = 'invitation_id_example' # String | 

begin
  # Revoke a pending workspace invitation.
  api_instance.revoke_workspace_invitation(workspace_id, invitation_id)
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->revoke_workspace_invitation: #{e}"
end
```

#### Using the revoke_workspace_invitation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_workspace_invitation_with_http_info(workspace_id, invitation_id)

```ruby
begin
  # Revoke a pending workspace invitation.
  data, status_code, headers = api_instance.revoke_workspace_invitation_with_http_info(workspace_id, invitation_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->revoke_workspace_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **invitation_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_workspace

> <WorkspaceEnvelope> update_workspace(workspace_id, update_workspace_request)

Update workspace metadata.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
update_workspace_request = Spatio::UpdateWorkspaceRequest.new # UpdateWorkspaceRequest | 

begin
  # Update workspace metadata.
  result = api_instance.update_workspace(workspace_id, update_workspace_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->update_workspace: #{e}"
end
```

#### Using the update_workspace_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceEnvelope>, Integer, Hash)> update_workspace_with_http_info(workspace_id, update_workspace_request)

```ruby
begin
  # Update workspace metadata.
  data, status_code, headers = api_instance.update_workspace_with_http_info(workspace_id, update_workspace_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->update_workspace_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **update_workspace_request** | [**UpdateWorkspaceRequest**](UpdateWorkspaceRequest.md) |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_workspace_member

> Hash&lt;String, Object&gt; update_workspace_member(workspace_id, member_id, update_workspace_member_request)

Update a member's role.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::WorkspacesApi.new
workspace_id = 'workspace_id_example' # String | 
member_id = 'member_id_example' # String | 
update_workspace_member_request = Spatio::UpdateWorkspaceMemberRequest.new({role: 'owner'}) # UpdateWorkspaceMemberRequest | 

begin
  # Update a member's role.
  result = api_instance.update_workspace_member(workspace_id, member_id, update_workspace_member_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->update_workspace_member: #{e}"
end
```

#### Using the update_workspace_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_workspace_member_with_http_info(workspace_id, member_id, update_workspace_member_request)

```ruby
begin
  # Update a member's role.
  data, status_code, headers = api_instance.update_workspace_member_with_http_info(workspace_id, member_id, update_workspace_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling WorkspacesApi->update_workspace_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  |  |
| **member_id** | **String** |  |  |
| **update_workspace_member_request** | [**UpdateWorkspaceMemberRequest**](UpdateWorkspaceMemberRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

