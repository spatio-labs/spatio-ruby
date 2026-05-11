# Spatio::OrganizationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**accept_organization_invitation**](OrganizationsApi.md#accept_organization_invitation) | **POST** /v1/organizations/{org}/accept-invitation | Accept an invitation to this organization. |
| [**add_organization_member**](OrganizationsApi.md#add_organization_member) | **POST** /v1/organizations/{org}/members | Add a member directly (skips invitation flow). |
| [**create_organization**](OrganizationsApi.md#create_organization) | **POST** /v1/organizations | Create an organization. |
| [**create_organization_concept**](OrganizationsApi.md#create_organization_concept) | **POST** /v1/organizations/{org}/concepts | Create an org-brain concept (admin+ only). |
| [**create_organization_custom_role**](OrganizationsApi.md#create_organization_custom_role) | **POST** /v1/organizations/{org}/roles | Create a custom role (admin+ only). |
| [**create_organization_invitation**](OrganizationsApi.md#create_organization_invitation) | **POST** /v1/organizations/{org}/invitations | Invite a user to the organization. |
| [**create_organization_workspace**](OrganizationsApi.md#create_organization_workspace) | **POST** /v1/organizations/{org}/workspaces | Create a workspace inside an organization. |
| [**delete_organization**](OrganizationsApi.md#delete_organization) | **DELETE** /v1/organizations/{org} | Delete an organization. |
| [**delete_organization_concept**](OrganizationsApi.md#delete_organization_concept) | **DELETE** /v1/organizations/{org}/concepts/{slug} | Delete a concept (admin+ only). |
| [**delete_organization_custom_role**](OrganizationsApi.md#delete_organization_custom_role) | **DELETE** /v1/organizations/{org}/roles/{roleId} | Delete a custom role (admin+ only). |
| [**delete_organization_logo**](OrganizationsApi.md#delete_organization_logo) | **DELETE** /v1/organizations/{org}/logo | Delete the organization logo. |
| [**get_organization**](OrganizationsApi.md#get_organization) | **GET** /v1/organizations/{org} | Fetch a single organization. |
| [**get_organization_concept**](OrganizationsApi.md#get_organization_concept) | **GET** /v1/organizations/{org}/concepts/{slug} | Fetch a concept. |
| [**list_my_organizations**](OrganizationsApi.md#list_my_organizations) | **GET** /v1/organizations | List the caller&#39;s organizations. |
| [**list_organization_audit_log**](OrganizationsApi.md#list_organization_audit_log) | **GET** /v1/organizations/{org}/audit-log | Read the organization audit log (admin / billing-admin only). |
| [**list_organization_concepts**](OrganizationsApi.md#list_organization_concepts) | **GET** /v1/organizations/{org}/concepts | List org-brain concepts (curated knowledge surfaced to agents). |
| [**list_organization_custom_roles**](OrganizationsApi.md#list_organization_custom_roles) | **GET** /v1/organizations/{org}/roles | List custom roles defined on the organization. |
| [**list_organization_invitations**](OrganizationsApi.md#list_organization_invitations) | **GET** /v1/organizations/{org}/invitations | List pending invitations for an organization. |
| [**list_organization_members**](OrganizationsApi.md#list_organization_members) | **GET** /v1/organizations/{org}/members | List members of an organization. |
| [**list_organization_workspaces**](OrganizationsApi.md#list_organization_workspaces) | **GET** /v1/organizations/{org}/workspaces | List workspaces in an organization. |
| [**remove_organization_member**](OrganizationsApi.md#remove_organization_member) | **DELETE** /v1/organizations/{org}/members/{memberId} | Remove a member from the organization. |
| [**resend_organization_invitation**](OrganizationsApi.md#resend_organization_invitation) | **POST** /v1/organizations/{org}/invitations/{invitationId}/resend | Revoke and reissue an invitation with a fresh token. |
| [**revoke_organization_invitation**](OrganizationsApi.md#revoke_organization_invitation) | **DELETE** /v1/organizations/{org}/invitations/{invitationId} | Revoke a pending invitation. |
| [**update_organization**](OrganizationsApi.md#update_organization) | **PATCH** /v1/organizations/{org} | Update organization metadata. |
| [**update_organization_concept**](OrganizationsApi.md#update_organization_concept) | **PATCH** /v1/organizations/{org}/concepts/{slug} | Update a concept (admin+ only). |
| [**update_organization_custom_role**](OrganizationsApi.md#update_organization_custom_role) | **PATCH** /v1/organizations/{org}/roles/{roleId} | Update a custom role (admin+ only). |
| [**update_organization_member**](OrganizationsApi.md#update_organization_member) | **PATCH** /v1/organizations/{org}/members/{memberId} | Update a member&#39;s role. |
| [**upload_organization_logo**](OrganizationsApi.md#upload_organization_logo) | **POST** /v1/organizations/{org}/logo | Upload (or replace) the organization logo. Multipart. |


## accept_organization_invitation

> Hash&lt;String, Object&gt; accept_organization_invitation(org, accept_organization_invitation_request)

Accept an invitation to this organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
accept_organization_invitation_request = Spatio::AcceptOrganizationInvitationRequest.new({token: 'token_example'}) # AcceptOrganizationInvitationRequest | 

begin
  # Accept an invitation to this organization.
  result = api_instance.accept_organization_invitation(org, accept_organization_invitation_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->accept_organization_invitation: #{e}"
end
```

#### Using the accept_organization_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> accept_organization_invitation_with_http_info(org, accept_organization_invitation_request)

```ruby
begin
  # Accept an invitation to this organization.
  data, status_code, headers = api_instance.accept_organization_invitation_with_http_info(org, accept_organization_invitation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->accept_organization_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **accept_organization_invitation_request** | [**AcceptOrganizationInvitationRequest**](AcceptOrganizationInvitationRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## add_organization_member

> Hash&lt;String, Object&gt; add_organization_member(org, add_organization_member_request)

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

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
add_organization_member_request = Spatio::AddOrganizationMemberRequest.new({email: 'email_example'}) # AddOrganizationMemberRequest | 

begin
  # Add a member directly (skips invitation flow).
  result = api_instance.add_organization_member(org, add_organization_member_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->add_organization_member: #{e}"
end
```

#### Using the add_organization_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> add_organization_member_with_http_info(org, add_organization_member_request)

```ruby
begin
  # Add a member directly (skips invitation flow).
  data, status_code, headers = api_instance.add_organization_member_with_http_info(org, add_organization_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->add_organization_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **add_organization_member_request** | [**AddOrganizationMemberRequest**](AddOrganizationMemberRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization

> Hash&lt;String, Object&gt; create_organization(create_organization_request)

Create an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
create_organization_request = Spatio::CreateOrganizationRequest.new({name: 'name_example'}) # CreateOrganizationRequest | 

begin
  # Create an organization.
  result = api_instance.create_organization(create_organization_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization: #{e}"
end
```

#### Using the create_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_organization_with_http_info(create_organization_request)

```ruby
begin
  # Create an organization.
  data, status_code, headers = api_instance.create_organization_with_http_info(create_organization_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_organization_request** | [**CreateOrganizationRequest**](CreateOrganizationRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization_concept

> Hash&lt;String, Object&gt; create_organization_concept(org, request_body)

Create an org-brain concept (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create an org-brain concept (admin+ only).
  result = api_instance.create_organization_concept(org, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_concept: #{e}"
end
```

#### Using the create_organization_concept_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_organization_concept_with_http_info(org, request_body)

```ruby
begin
  # Create an org-brain concept (admin+ only).
  data, status_code, headers = api_instance.create_organization_concept_with_http_info(org, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_concept_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization_custom_role

> Hash&lt;String, Object&gt; create_organization_custom_role(org, request_body)

Create a custom role (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create a custom role (admin+ only).
  result = api_instance.create_organization_custom_role(org, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_custom_role: #{e}"
end
```

#### Using the create_organization_custom_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_organization_custom_role_with_http_info(org, request_body)

```ruby
begin
  # Create a custom role (admin+ only).
  data, status_code, headers = api_instance.create_organization_custom_role_with_http_info(org, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_custom_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization_invitation

> <OrganizationInvitation> create_organization_invitation(org, create_organization_invitation_request)

Invite a user to the organization.

Pending invitations count toward seat cap. Free-tier callers at the cap receive a `402` with billing-upgrade payload; paid-tier auto-scales the Stripe quantity. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
create_organization_invitation_request = Spatio::CreateOrganizationInvitationRequest.new({email: 'email_example', role: 'owner'}) # CreateOrganizationInvitationRequest | 

begin
  # Invite a user to the organization.
  result = api_instance.create_organization_invitation(org, create_organization_invitation_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_invitation: #{e}"
end
```

#### Using the create_organization_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationInvitation>, Integer, Hash)> create_organization_invitation_with_http_info(org, create_organization_invitation_request)

```ruby
begin
  # Invite a user to the organization.
  data, status_code, headers = api_instance.create_organization_invitation_with_http_info(org, create_organization_invitation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationInvitation>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **create_organization_invitation_request** | [**CreateOrganizationInvitationRequest**](CreateOrganizationInvitationRequest.md) |  |  |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_organization_workspace

> <WorkspaceEnvelope> create_organization_workspace(org, create_workspace_request)

Create a workspace inside an organization.

Requires the `OrgActionCreateWorkspace` action permission. Slug collisions auto-suffix (`-2`, `-3`, ...). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
create_workspace_request = Spatio::CreateWorkspaceRequest.new({name: 'name_example'}) # CreateWorkspaceRequest | 

begin
  # Create a workspace inside an organization.
  result = api_instance.create_organization_workspace(org, create_workspace_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_workspace: #{e}"
end
```

#### Using the create_organization_workspace_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceEnvelope>, Integer, Hash)> create_organization_workspace_with_http_info(org, create_workspace_request)

```ruby
begin
  # Create a workspace inside an organization.
  data, status_code, headers = api_instance.create_organization_workspace_with_http_info(org, create_workspace_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->create_organization_workspace_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **create_workspace_request** | [**CreateWorkspaceRequest**](CreateWorkspaceRequest.md) |  |  |

### Return type

[**WorkspaceEnvelope**](WorkspaceEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_organization

> delete_organization(org)

Delete an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | Organization id or slug.

begin
  # Delete an organization.
  api_instance.delete_organization(org)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization: #{e}"
end
```

#### Using the delete_organization_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_organization_with_http_info(org)

```ruby
begin
  # Delete an organization.
  data, status_code, headers = api_instance.delete_organization_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** | Organization id or slug. |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_organization_concept

> delete_organization_concept(org, slug)

Delete a concept (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
slug = 'slug_example' # String | 

begin
  # Delete a concept (admin+ only).
  api_instance.delete_organization_concept(org, slug)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_concept: #{e}"
end
```

#### Using the delete_organization_concept_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_organization_concept_with_http_info(org, slug)

```ruby
begin
  # Delete a concept (admin+ only).
  data, status_code, headers = api_instance.delete_organization_concept_with_http_info(org, slug)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_concept_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **slug** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_organization_custom_role

> delete_organization_custom_role(org, role_id)

Delete a custom role (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
role_id = 'role_id_example' # String | 

begin
  # Delete a custom role (admin+ only).
  api_instance.delete_organization_custom_role(org, role_id)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_custom_role: #{e}"
end
```

#### Using the delete_organization_custom_role_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_organization_custom_role_with_http_info(org, role_id)

```ruby
begin
  # Delete a custom role (admin+ only).
  data, status_code, headers = api_instance.delete_organization_custom_role_with_http_info(org, role_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_custom_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **role_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_organization_logo

> delete_organization_logo(org)

Delete the organization logo.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # Delete the organization logo.
  api_instance.delete_organization_logo(org)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_logo: #{e}"
end
```

#### Using the delete_organization_logo_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_organization_logo_with_http_info(org)

```ruby
begin
  # Delete the organization logo.
  data, status_code, headers = api_instance.delete_organization_logo_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->delete_organization_logo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization

> <OrganizationDetailLegacy> get_organization(org)

Fetch a single organization.

**Wire format note:** response uses PascalCase keys (`ID`, `Name`, `Slug`, ...) — distinct from the rest of the SpatioAPI's camelCase convention. Documented as-is; a future cleanup will harmonize. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | Organization id or slug.

begin
  # Fetch a single organization.
  result = api_instance.get_organization(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization: #{e}"
end
```

#### Using the get_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationDetailLegacy>, Integer, Hash)> get_organization_with_http_info(org)

```ruby
begin
  # Fetch a single organization.
  data, status_code, headers = api_instance.get_organization_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationDetailLegacy>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** | Organization id or slug. |  |

### Return type

[**OrganizationDetailLegacy**](OrganizationDetailLegacy.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_organization_concept

> Hash&lt;String, Object&gt; get_organization_concept(org, slug)

Fetch a concept.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
slug = 'slug_example' # String | 

begin
  # Fetch a concept.
  result = api_instance.get_organization_concept(org, slug)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_concept: #{e}"
end
```

#### Using the get_organization_concept_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_organization_concept_with_http_info(org, slug)

```ruby
begin
  # Fetch a concept.
  data, status_code, headers = api_instance.get_organization_concept_with_http_info(org, slug)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->get_organization_concept_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **slug** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_my_organizations

> <OrganizationListResponse> list_my_organizations

List the caller's organizations.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new

begin
  # List the caller's organizations.
  result = api_instance.list_my_organizations
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_my_organizations: #{e}"
end
```

#### Using the list_my_organizations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationListResponse>, Integer, Hash)> list_my_organizations_with_http_info

```ruby
begin
  # List the caller's organizations.
  data, status_code, headers = api_instance.list_my_organizations_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_my_organizations_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**OrganizationListResponse**](OrganizationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_audit_log

> Hash&lt;String, Object&gt; list_organization_audit_log(org, opts)

Read the organization audit log (admin / billing-admin only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
opts = {
  limit: 56, # Integer | 
  cursor: 'cursor_example' # String | 
}

begin
  # Read the organization audit log (admin / billing-admin only).
  result = api_instance.list_organization_audit_log(org, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_audit_log: #{e}"
end
```

#### Using the list_organization_audit_log_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_organization_audit_log_with_http_info(org, opts)

```ruby
begin
  # Read the organization audit log (admin / billing-admin only).
  data, status_code, headers = api_instance.list_organization_audit_log_with_http_info(org, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_audit_log_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **limit** | **Integer** |  | [optional] |
| **cursor** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_concepts

> Hash&lt;String, Object&gt; list_organization_concepts(org)

List org-brain concepts (curated knowledge surfaced to agents).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # List org-brain concepts (curated knowledge surfaced to agents).
  result = api_instance.list_organization_concepts(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_concepts: #{e}"
end
```

#### Using the list_organization_concepts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_organization_concepts_with_http_info(org)

```ruby
begin
  # List org-brain concepts (curated knowledge surfaced to agents).
  data, status_code, headers = api_instance.list_organization_concepts_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_concepts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_custom_roles

> Hash&lt;String, Object&gt; list_organization_custom_roles(org)

List custom roles defined on the organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # List custom roles defined on the organization.
  result = api_instance.list_organization_custom_roles(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_custom_roles: #{e}"
end
```

#### Using the list_organization_custom_roles_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_organization_custom_roles_with_http_info(org)

```ruby
begin
  # List custom roles defined on the organization.
  data, status_code, headers = api_instance.list_organization_custom_roles_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_custom_roles_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_invitations

> <OrganizationInvitationListResponse> list_organization_invitations(org)

List pending invitations for an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # List pending invitations for an organization.
  result = api_instance.list_organization_invitations(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_invitations: #{e}"
end
```

#### Using the list_organization_invitations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationInvitationListResponse>, Integer, Hash)> list_organization_invitations_with_http_info(org)

```ruby
begin
  # List pending invitations for an organization.
  data, status_code, headers = api_instance.list_organization_invitations_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationInvitationListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_invitations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

[**OrganizationInvitationListResponse**](OrganizationInvitationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_members

> <OrganizationMemberListResponse> list_organization_members(org)

List members of an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # List members of an organization.
  result = api_instance.list_organization_members(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_members: #{e}"
end
```

#### Using the list_organization_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationMemberListResponse>, Integer, Hash)> list_organization_members_with_http_info(org)

```ruby
begin
  # List members of an organization.
  data, status_code, headers = api_instance.list_organization_members_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationMemberListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

[**OrganizationMemberListResponse**](OrganizationMemberListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_organization_workspaces

> <WorkspaceListResponse> list_organization_workspaces(org)

List workspaces in an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 

begin
  # List workspaces in an organization.
  result = api_instance.list_organization_workspaces(org)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_workspaces: #{e}"
end
```

#### Using the list_organization_workspaces_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<WorkspaceListResponse>, Integer, Hash)> list_organization_workspaces_with_http_info(org)

```ruby
begin
  # List workspaces in an organization.
  data, status_code, headers = api_instance.list_organization_workspaces_with_http_info(org)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <WorkspaceListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->list_organization_workspaces_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |

### Return type

[**WorkspaceListResponse**](WorkspaceListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_organization_member

> remove_organization_member(org, member_id)

Remove a member from the organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
member_id = 'member_id_example' # String | 

begin
  # Remove a member from the organization.
  api_instance.remove_organization_member(org, member_id)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->remove_organization_member: #{e}"
end
```

#### Using the remove_organization_member_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> remove_organization_member_with_http_info(org, member_id)

```ruby
begin
  # Remove a member from the organization.
  data, status_code, headers = api_instance.remove_organization_member_with_http_info(org, member_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->remove_organization_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **member_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## resend_organization_invitation

> <OrganizationInvitation> resend_organization_invitation(org, invitation_id)

Revoke and reissue an invitation with a fresh token.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
invitation_id = 'invitation_id_example' # String | 

begin
  # Revoke and reissue an invitation with a fresh token.
  result = api_instance.resend_organization_invitation(org, invitation_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->resend_organization_invitation: #{e}"
end
```

#### Using the resend_organization_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OrganizationInvitation>, Integer, Hash)> resend_organization_invitation_with_http_info(org, invitation_id)

```ruby
begin
  # Revoke and reissue an invitation with a fresh token.
  data, status_code, headers = api_instance.resend_organization_invitation_with_http_info(org, invitation_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OrganizationInvitation>
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->resend_organization_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **invitation_id** | **String** |  |  |

### Return type

[**OrganizationInvitation**](OrganizationInvitation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_organization_invitation

> revoke_organization_invitation(org, invitation_id)

Revoke a pending invitation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
invitation_id = 'invitation_id_example' # String | 

begin
  # Revoke a pending invitation.
  api_instance.revoke_organization_invitation(org, invitation_id)
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->revoke_organization_invitation: #{e}"
end
```

#### Using the revoke_organization_invitation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> revoke_organization_invitation_with_http_info(org, invitation_id)

```ruby
begin
  # Revoke a pending invitation.
  data, status_code, headers = api_instance.revoke_organization_invitation_with_http_info(org, invitation_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->revoke_organization_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **invitation_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_organization

> Hash&lt;String, Object&gt; update_organization(org, update_organization_request)

Update organization metadata.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | Organization id or slug.
update_organization_request = Spatio::UpdateOrganizationRequest.new # UpdateOrganizationRequest | 

begin
  # Update organization metadata.
  result = api_instance.update_organization(org, update_organization_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization: #{e}"
end
```

#### Using the update_organization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_organization_with_http_info(org, update_organization_request)

```ruby
begin
  # Update organization metadata.
  data, status_code, headers = api_instance.update_organization_with_http_info(org, update_organization_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** | Organization id or slug. |  |
| **update_organization_request** | [**UpdateOrganizationRequest**](UpdateOrganizationRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_organization_concept

> Hash&lt;String, Object&gt; update_organization_concept(org, slug, request_body)

Update a concept (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
slug = 'slug_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update a concept (admin+ only).
  result = api_instance.update_organization_concept(org, slug, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_concept: #{e}"
end
```

#### Using the update_organization_concept_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_organization_concept_with_http_info(org, slug, request_body)

```ruby
begin
  # Update a concept (admin+ only).
  data, status_code, headers = api_instance.update_organization_concept_with_http_info(org, slug, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_concept_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **slug** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_organization_custom_role

> Hash&lt;String, Object&gt; update_organization_custom_role(org, role_id, request_body)

Update a custom role (admin+ only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
role_id = 'role_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update a custom role (admin+ only).
  result = api_instance.update_organization_custom_role(org, role_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_custom_role: #{e}"
end
```

#### Using the update_organization_custom_role_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_organization_custom_role_with_http_info(org, role_id, request_body)

```ruby
begin
  # Update a custom role (admin+ only).
  data, status_code, headers = api_instance.update_organization_custom_role_with_http_info(org, role_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_custom_role_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **role_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_organization_member

> Hash&lt;String, Object&gt; update_organization_member(org, member_id, update_organization_member_request)

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

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
member_id = 'member_id_example' # String | 
update_organization_member_request = Spatio::UpdateOrganizationMemberRequest.new({role: 'owner'}) # UpdateOrganizationMemberRequest | 

begin
  # Update a member's role.
  result = api_instance.update_organization_member(org, member_id, update_organization_member_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_member: #{e}"
end
```

#### Using the update_organization_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_organization_member_with_http_info(org, member_id, update_organization_member_request)

```ruby
begin
  # Update a member's role.
  data, status_code, headers = api_instance.update_organization_member_with_http_info(org, member_id, update_organization_member_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->update_organization_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **member_id** | **String** |  |  |
| **update_organization_member_request** | [**UpdateOrganizationMemberRequest**](UpdateOrganizationMemberRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## upload_organization_logo

> Hash&lt;String, Object&gt; upload_organization_logo(org, opts)

Upload (or replace) the organization logo. Multipart.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::OrganizationsApi.new
org = 'org_example' # String | 
opts = {
  file: File.new('/path/to/some/file') # File | 
}

begin
  # Upload (or replace) the organization logo. Multipart.
  result = api_instance.upload_organization_logo(org, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->upload_organization_logo: #{e}"
end
```

#### Using the upload_organization_logo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> upload_organization_logo_with_http_info(org, opts)

```ruby
begin
  # Upload (or replace) the organization logo. Multipart.
  data, status_code, headers = api_instance.upload_organization_logo_with_http_info(org, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling OrganizationsApi->upload_organization_logo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **file** | **File** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

