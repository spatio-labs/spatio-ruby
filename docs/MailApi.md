# Spatio::MailApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**bulk_archive_emails**](MailApi.md#bulk_archive_emails) | **POST** /v1/mail/archive | Archive multiple messages (remove the INBOX label). |
| [**bulk_delete_emails**](MailApi.md#bulk_delete_emails) | **POST** /v1/mail/delete | Delete multiple messages in one call. |
| [**bulk_mark_emails_read**](MailApi.md#bulk_mark_emails_read) | **POST** /v1/mail/mark-read | Mark multiple messages read or unread in one call. |
| [**create_draft**](MailApi.md#create_draft) | **POST** /v1/mail/drafts | Create a draft. |
| [**create_email_label**](MailApi.md#create_email_label) | **POST** /v1/mail/labels | Create a label. |
| [**create_mail_template**](MailApi.md#create_mail_template) | **POST** /v1/mail/templates | Create a mail template. |
| [**delete_draft**](MailApi.md#delete_draft) | **DELETE** /v1/mail/drafts/{id} | Delete a draft. |
| [**delete_email**](MailApi.md#delete_email) | **DELETE** /v1/mail/email/{id} | Delete an email. |
| [**delete_email_label**](MailApi.md#delete_email_label) | **DELETE** /v1/mail/labels/{id} | Delete a label. |
| [**delete_mail_template**](MailApi.md#delete_mail_template) | **DELETE** /v1/mail/templates/{id} | Delete a mail template. |
| [**get_email**](MailApi.md#get_email) | **GET** /v1/mail/email/{id} | Fetch one email. |
| [**get_email_attachment**](MailApi.md#get_email_attachment) | **GET** /v1/mail/attachment/{messageId}/{attachmentId} | Download an attachment. |
| [**get_email_thread**](MailApi.md#get_email_thread) | **GET** /v1/mail/thread/{id} | Fetch a thread (the conversation a message belongs to). |
| [**get_mail_template**](MailApi.md#get_mail_template) | **GET** /v1/mail/templates/{id} | Fetch a mail template. |
| [**get_mail_thread_tracking**](MailApi.md#get_mail_thread_tracking) | **GET** /v1/mail/threads/{threadId}/tracking | Read mail-tracking events for a thread (open log, reply log, etc.). |
| [**instantiate_mail_template**](MailApi.md#instantiate_mail_template) | **POST** /v1/mail/templates/{id}/instantiate | Render a template with variables and return the resulting draft. |
| [**list_drafts**](MailApi.md#list_drafts) | **GET** /v1/mail/drafts | List drafts across connected mail accounts. |
| [**list_email_labels**](MailApi.md#list_email_labels) | **GET** /v1/mail/labels | List labels on the resolved mail account. |
| [**list_emails**](MailApi.md#list_emails) | **GET** /v1/mail/list | List emails across connected mail accounts. |
| [**list_mail_templates**](MailApi.md#list_mail_templates) | **GET** /v1/mail/templates | List the caller&#39;s saved mail templates. |
| [**reply_email**](MailApi.md#reply_email) | **POST** /v1/mail/reply | Reply to a specific email. |
| [**save_mail_template**](MailApi.md#save_mail_template) | **POST** /v1/mail/templates/save | Save-or-create endpoint used by the renderer&#39;s \&quot;save as template\&quot; flow. Distinct from POST /v1/mail/templates which is the strict create.  |
| [**search_emails**](MailApi.md#search_emails) | **GET** /v1/mail/search | Structured search across connected mail accounts. |
| [**send_draft**](MailApi.md#send_draft) | **POST** /v1/mail/drafts/{id}/send | Send a draft. |
| [**send_email**](MailApi.md#send_email) | **POST** /v1/mail/send | Send an email. |
| [**update_draft**](MailApi.md#update_draft) | **PUT** /v1/mail/drafts/{id} | Update a draft (full replacement of provided fields). |
| [**update_email**](MailApi.md#update_email) | **PATCH** /v1/mail/email/{id} | Update an email (mark read/star, add/remove labels). |
| [**update_mail_template**](MailApi.md#update_mail_template) | **PATCH** /v1/mail/templates/{id} | Update a mail template. |
| [**workspace_add_mail_message_labels**](MailApi.md#workspace_add_mail_message_labels) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/{messageId}/labels |  |
| [**workspace_create_mail_draft**](MailApi.md#workspace_create_mail_draft) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts |  |
| [**workspace_create_mail_label**](MailApi.md#workspace_create_mail_label) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/labels |  |
| [**workspace_delete_mail**](MailApi.md#workspace_delete_mail) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspace_delete_mail_draft**](MailApi.md#workspace_delete_mail_draft) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspace_delete_mail_label**](MailApi.md#workspace_delete_mail_label) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/labels/{id} |  |
| [**workspace_get_mail**](MailApi.md#workspace_get_mail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspace_get_mail_attachment**](MailApi.md#workspace_get_mail_attachment) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/attachment/{messageId}/{attachmentId} |  |
| [**workspace_get_mail_by_id**](MailApi.md#workspace_get_mail_by_id) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/{id} | Workspace-scoped renderer-compat alias for mail/email/{id}. |
| [**workspace_get_mail_draft**](MailApi.md#workspace_get_mail_draft) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspace_get_mail_thread**](MailApi.md#workspace_get_mail_thread) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/thread/{id} |  |
| [**workspace_list_mail**](MailApi.md#workspace_list_mail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/list |  |
| [**workspace_list_mail_drafts**](MailApi.md#workspace_list_mail_drafts) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts |  |
| [**workspace_list_mail_labels**](MailApi.md#workspace_list_mail_labels) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/labels |  |
| [**workspace_patch_mail**](MailApi.md#workspace_patch_mail) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspace_remove_mail_message_label**](MailApi.md#workspace_remove_mail_message_label) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/mail/{messageId}/labels/{labelId} |  |
| [**workspace_reply_mail**](MailApi.md#workspace_reply_mail) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/reply |  |
| [**workspace_search_mail**](MailApi.md#workspace_search_mail) | **GET** /v1/organizations/{org}/workspaces/{workspace}/mail/search |  |
| [**workspace_send_mail**](MailApi.md#workspace_send_mail) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/send |  |
| [**workspace_send_mail_draft**](MailApi.md#workspace_send_mail_draft) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id}/send |  |
| [**workspace_send_mail_email_alias**](MailApi.md#workspace_send_mail_email_alias) | **POST** /v1/organizations/{org}/workspaces/{workspace}/mail/email | Renderer-compat alias for /mail/send. |
| [**workspace_update_mail**](MailApi.md#workspace_update_mail) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/email/{id} |  |
| [**workspace_update_mail_draft**](MailApi.md#workspace_update_mail_draft) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/drafts/{id} |  |
| [**workspace_update_mail_label**](MailApi.md#workspace_update_mail_label) | **PUT** /v1/organizations/{org}/workspaces/{workspace}/mail/labels/{id} |  |


## bulk_archive_emails

> <BulkArchiveResponse> bulk_archive_emails(bulk_archive_request)

Archive multiple messages (remove the INBOX label).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
bulk_archive_request = Spatio::BulkArchiveRequest.new({message_ids: ['message_ids_example']}) # BulkArchiveRequest | 

begin
  # Archive multiple messages (remove the INBOX label).
  result = api_instance.bulk_archive_emails(bulk_archive_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_archive_emails: #{e}"
end
```

#### Using the bulk_archive_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkArchiveResponse>, Integer, Hash)> bulk_archive_emails_with_http_info(bulk_archive_request)

```ruby
begin
  # Archive multiple messages (remove the INBOX label).
  data, status_code, headers = api_instance.bulk_archive_emails_with_http_info(bulk_archive_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkArchiveResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_archive_emails_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_archive_request** | [**BulkArchiveRequest**](BulkArchiveRequest.md) |  |  |

### Return type

[**BulkArchiveResponse**](BulkArchiveResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## bulk_delete_emails

> <BulkDeleteEmailsResponse> bulk_delete_emails(bulk_delete_emails_request)

Delete multiple messages in one call.

Soft-delete by default (moves to provider trash). Set `permanent: true` for a hard delete. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
bulk_delete_emails_request = Spatio::BulkDeleteEmailsRequest.new({message_ids: ['message_ids_example']}) # BulkDeleteEmailsRequest | 

begin
  # Delete multiple messages in one call.
  result = api_instance.bulk_delete_emails(bulk_delete_emails_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_delete_emails: #{e}"
end
```

#### Using the bulk_delete_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkDeleteEmailsResponse>, Integer, Hash)> bulk_delete_emails_with_http_info(bulk_delete_emails_request)

```ruby
begin
  # Delete multiple messages in one call.
  data, status_code, headers = api_instance.bulk_delete_emails_with_http_info(bulk_delete_emails_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkDeleteEmailsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_delete_emails_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_delete_emails_request** | [**BulkDeleteEmailsRequest**](BulkDeleteEmailsRequest.md) |  |  |

### Return type

[**BulkDeleteEmailsResponse**](BulkDeleteEmailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## bulk_mark_emails_read

> <BulkMarkReadResponse> bulk_mark_emails_read(bulk_mark_read_request)

Mark multiple messages read or unread in one call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
bulk_mark_read_request = Spatio::BulkMarkReadRequest.new({message_ids: ['message_ids_example']}) # BulkMarkReadRequest | 

begin
  # Mark multiple messages read or unread in one call.
  result = api_instance.bulk_mark_emails_read(bulk_mark_read_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_mark_emails_read: #{e}"
end
```

#### Using the bulk_mark_emails_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkMarkReadResponse>, Integer, Hash)> bulk_mark_emails_read_with_http_info(bulk_mark_read_request)

```ruby
begin
  # Mark multiple messages read or unread in one call.
  data, status_code, headers = api_instance.bulk_mark_emails_read_with_http_info(bulk_mark_read_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkMarkReadResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->bulk_mark_emails_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_mark_read_request** | [**BulkMarkReadRequest**](BulkMarkReadRequest.md) |  |  |

### Return type

[**BulkMarkReadResponse**](BulkMarkReadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_draft

> <DraftResponse> create_draft(create_draft_request, opts)

Create a draft.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
create_draft_request = Spatio::CreateDraftRequest.new # CreateDraftRequest | 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a draft.
  result = api_instance.create_draft(create_draft_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_draft: #{e}"
end
```

#### Using the create_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftResponse>, Integer, Hash)> create_draft_with_http_info(create_draft_request, opts)

```ruby
begin
  # Create a draft.
  data, status_code, headers = api_instance.create_draft_with_http_info(create_draft_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_draft_request** | [**CreateDraftRequest**](CreateDraftRequest.md) |  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**DraftResponse**](DraftResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_email_label

> <CreateLabelResponse> create_email_label(create_label_request, opts)

Create a label.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
create_label_request = Spatio::CreateLabelRequest.new({name: 'name_example'}) # CreateLabelRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a label.
  result = api_instance.create_email_label(create_label_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_email_label: #{e}"
end
```

#### Using the create_email_label_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateLabelResponse>, Integer, Hash)> create_email_label_with_http_info(create_label_request, opts)

```ruby
begin
  # Create a label.
  data, status_code, headers = api_instance.create_email_label_with_http_info(create_label_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateLabelResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_email_label_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_label_request** | [**CreateLabelRequest**](CreateLabelRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CreateLabelResponse**](CreateLabelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_mail_template

> Hash&lt;String, Object&gt; create_mail_template(request_body)

Create a mail template.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create a mail template.
  result = api_instance.create_mail_template(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_mail_template: #{e}"
end
```

#### Using the create_mail_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_mail_template_with_http_info(request_body)

```ruby
begin
  # Create a mail template.
  data, status_code, headers = api_instance.create_mail_template_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->create_mail_template_with_http_info: #{e}"
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


## delete_draft

> delete_draft(id, opts)

Delete a draft.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Draft id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a draft.
  api_instance.delete_draft(id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_draft: #{e}"
end
```

#### Using the delete_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_draft_with_http_info(id, opts)

```ruby
begin
  # Delete a draft.
  data, status_code, headers = api_instance.delete_draft_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Draft id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_email

> <SuccessFlag> delete_email(id, opts)

Delete an email.

Soft-deletes (moves to provider trash).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Email message id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete an email.
  result = api_instance.delete_email(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_email: #{e}"
end
```

#### Using the delete_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_email_with_http_info(id, opts)

```ruby
begin
  # Delete an email.
  data, status_code, headers = api_instance.delete_email_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Email message id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_email_label

> delete_email_label(id, opts)

Delete a label.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Label id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a label.
  api_instance.delete_email_label(id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_email_label: #{e}"
end
```

#### Using the delete_email_label_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_email_label_with_http_info(id, opts)

```ruby
begin
  # Delete a label.
  data, status_code, headers = api_instance.delete_email_label_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_email_label_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Label id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_mail_template

> delete_mail_template(id)

Delete a mail template.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | 

begin
  # Delete a mail template.
  api_instance.delete_mail_template(id)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_mail_template: #{e}"
end
```

#### Using the delete_mail_template_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_mail_template_with_http_info(id)

```ruby
begin
  # Delete a mail template.
  data, status_code, headers = api_instance.delete_mail_template_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->delete_mail_template_with_http_info: #{e}"
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


## get_email

> <GetEmailResponse> get_email(id, opts)

Fetch one email.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Email message id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one email.
  result = api_instance.get_email(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email: #{e}"
end
```

#### Using the get_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetEmailResponse>, Integer, Hash)> get_email_with_http_info(id, opts)

```ruby
begin
  # Fetch one email.
  data, status_code, headers = api_instance.get_email_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetEmailResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Email message id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**GetEmailResponse**](GetEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_email_attachment

> File get_email_attachment(message_id, attachment_id, opts)

Download an attachment.

Streams the attachment binary. Response `Content-Type` matches the attachment's declared MIME type; `Content-Disposition` sets the filename. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
message_id = 'message_id_example' # String | Message id the attachment belongs to.
attachment_id = 'attachment_id_example' # String | Attachment id within the message.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Download an attachment.
  result = api_instance.get_email_attachment(message_id, attachment_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email_attachment: #{e}"
end
```

#### Using the get_email_attachment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> get_email_attachment_with_http_info(message_id, attachment_id, opts)

```ruby
begin
  # Download an attachment.
  data, status_code, headers = api_instance.get_email_attachment_with_http_info(message_id, attachment_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email_attachment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Message id the attachment belongs to. |  |
| **attachment_id** | **String** | Attachment id within the message. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

**File**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/octet-stream, application/json


## get_email_thread

> <GetThreadResponse> get_email_thread(id, opts)

Fetch a thread (the conversation a message belongs to).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Thread id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch a thread (the conversation a message belongs to).
  result = api_instance.get_email_thread(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email_thread: #{e}"
end
```

#### Using the get_email_thread_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetThreadResponse>, Integer, Hash)> get_email_thread_with_http_info(id, opts)

```ruby
begin
  # Fetch a thread (the conversation a message belongs to).
  data, status_code, headers = api_instance.get_email_thread_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetThreadResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_email_thread_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Thread id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**GetThreadResponse**](GetThreadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_mail_template

> Hash&lt;String, Object&gt; get_mail_template(id)

Fetch a mail template.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | 

begin
  # Fetch a mail template.
  result = api_instance.get_mail_template(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_mail_template: #{e}"
end
```

#### Using the get_mail_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_mail_template_with_http_info(id)

```ruby
begin
  # Fetch a mail template.
  data, status_code, headers = api_instance.get_mail_template_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_mail_template_with_http_info: #{e}"
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


## get_mail_thread_tracking

> Hash&lt;String, Object&gt; get_mail_thread_tracking(thread_id)

Read mail-tracking events for a thread (open log, reply log, etc.).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
thread_id = 'thread_id_example' # String | 

begin
  # Read mail-tracking events for a thread (open log, reply log, etc.).
  result = api_instance.get_mail_thread_tracking(thread_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_mail_thread_tracking: #{e}"
end
```

#### Using the get_mail_thread_tracking_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_mail_thread_tracking_with_http_info(thread_id)

```ruby
begin
  # Read mail-tracking events for a thread (open log, reply log, etc.).
  data, status_code, headers = api_instance.get_mail_thread_tracking_with_http_info(thread_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->get_mail_thread_tracking_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **thread_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## instantiate_mail_template

> Hash&lt;String, Object&gt; instantiate_mail_template(id, request_body)

Render a template with variables and return the resulting draft.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Render a template with variables and return the resulting draft.
  result = api_instance.instantiate_mail_template(id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->instantiate_mail_template: #{e}"
end
```

#### Using the instantiate_mail_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> instantiate_mail_template_with_http_info(id, request_body)

```ruby
begin
  # Render a template with variables and return the resulting draft.
  data, status_code, headers = api_instance.instantiate_mail_template_with_http_info(id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->instantiate_mail_template_with_http_info: #{e}"
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


## list_drafts

> <ListDraftsResponse> list_drafts(opts)

List drafts across connected mail accounts.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
opts = {
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  limit: 56, # Integer | 
  next_page_token: 'next_page_token_example' # String | 
}

begin
  # List drafts across connected mail accounts.
  result = api_instance.list_drafts(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_drafts: #{e}"
end
```

#### Using the list_drafts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListDraftsResponse>, Integer, Hash)> list_drafts_with_http_info(opts)

```ruby
begin
  # List drafts across connected mail accounts.
  data, status_code, headers = api_instance.list_drafts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListDraftsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_drafts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **next_page_token** | **String** |  | [optional] |

### Return type

[**ListDraftsResponse**](ListDraftsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_email_labels

> <ListLabelsResponse> list_email_labels(opts)

List labels on the resolved mail account.

Single-account list. The platform auto-resolves to the caller's sole connected account; pass `?accountId=` to disambiguate when multiple are connected. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # List labels on the resolved mail account.
  result = api_instance.list_email_labels(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_email_labels: #{e}"
end
```

#### Using the list_email_labels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListLabelsResponse>, Integer, Hash)> list_email_labels_with_http_info(opts)

```ruby
begin
  # List labels on the resolved mail account.
  data, status_code, headers = api_instance.list_email_labels_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListLabelsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_email_labels_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ListLabelsResponse**](ListLabelsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_emails

> <ListEmailsResponse> list_emails(opts)

List emails across connected mail accounts.

Fan-out list. Returns messages across every connected mail provider unless filtered. Pass `?accountIds=` (repeatable) to restrict to specific accounts, `?providers=` to restrict to specific provider ids, or both for the intersection. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  query: 'query_example', # String | Provider-specific full-text query (e.g. Gmail search syntax).
  labels: ['inner_example'], # Array<String> | Repeatable. Filter to messages carrying every label.
  folder: 'folder_example', # String | Logical folder filter. Canonical values: `inbox`, `sent`, `starred`, `trash`, `archive`. Provider-specific folders accepted as opaque strings. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List emails across connected mail accounts.
  result = api_instance.list_emails(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_emails: #{e}"
end
```

#### Using the list_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListEmailsResponse>, Integer, Hash)> list_emails_with_http_info(opts)

```ruby
begin
  # List emails across connected mail accounts.
  data, status_code, headers = api_instance.list_emails_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListEmailsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_emails_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **query** | **String** | Provider-specific full-text query (e.g. Gmail search syntax). | [optional] |
| **labels** | [**Array&lt;String&gt;**](String.md) | Repeatable. Filter to messages carrying every label. | [optional] |
| **folder** | **String** | Logical folder filter. Canonical values: &#x60;inbox&#x60;, &#x60;sent&#x60;, &#x60;starred&#x60;, &#x60;trash&#x60;, &#x60;archive&#x60;. Provider-specific folders accepted as opaque strings.  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**ListEmailsResponse**](ListEmailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_mail_templates

> Hash&lt;String, Object&gt; list_mail_templates

List the caller's saved mail templates.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new

begin
  # List the caller's saved mail templates.
  result = api_instance.list_mail_templates
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_mail_templates: #{e}"
end
```

#### Using the list_mail_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_mail_templates_with_http_info

```ruby
begin
  # List the caller's saved mail templates.
  data, status_code, headers = api_instance.list_mail_templates_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->list_mail_templates_with_http_info: #{e}"
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


## reply_email

> <SendEmailResponse> reply_email(message_id, reply_email_request, opts)

Reply to a specific email.

The original message is identified by `?messageId=`. Body defaults to the original sender as recipient — pass `to`, `cc`, `bcc` to override. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
message_id = 'message_id_example' # String | Id of the message being replied to.
reply_email_request = Spatio::ReplyEmailRequest.new({body: 'body_example'}) # ReplyEmailRequest | 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Reply to a specific email.
  result = api_instance.reply_email(message_id, reply_email_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->reply_email: #{e}"
end
```

#### Using the reply_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailResponse>, Integer, Hash)> reply_email_with_http_info(message_id, reply_email_request, opts)

```ruby
begin
  # Reply to a specific email.
  data, status_code, headers = api_instance.reply_email_with_http_info(message_id, reply_email_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->reply_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | Id of the message being replied to. |  |
| **reply_email_request** | [**ReplyEmailRequest**](ReplyEmailRequest.md) |  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## save_mail_template

> Hash&lt;String, Object&gt; save_mail_template(request_body)

Save-or-create endpoint used by the renderer's \"save as template\" flow. Distinct from POST /v1/mail/templates which is the strict create. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Save-or-create endpoint used by the renderer's \"save as template\" flow. Distinct from POST /v1/mail/templates which is the strict create. 
  result = api_instance.save_mail_template(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->save_mail_template: #{e}"
end
```

#### Using the save_mail_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> save_mail_template_with_http_info(request_body)

```ruby
begin
  # Save-or-create endpoint used by the renderer's \"save as template\" flow. Distinct from POST /v1/mail/templates which is the strict create. 
  data, status_code, headers = api_instance.save_mail_template_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->save_mail_template_with_http_info: #{e}"
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


## search_emails

> <SearchEmailsResponse> search_emails(q, opts)

Structured search across connected mail accounts.

Fan-out search. Mirrors `listEmails`'s account/provider filter semantics. Date range filters are inclusive. The query string itself is passed via `?q=` (not `?query=`); structured filters go in their own params. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
q = 'q_example' # String | Provider-specific full-text query string.
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to `providers` — when both are set the intersection is used. 
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to these provider ids (`gmail`, `outlook`).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  from: 'from_example', # String | 
  to: 'to_example', # String | 
  subject: 'subject_example', # String | 
  has_attachment: true, # Boolean | 
  is_unread: true, # Boolean | 
  is_starred: true, # Boolean | 
  labels: ['inner_example'], # Array<String> | 
  after: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Inclusive lower-bound date.
  before: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Inclusive upper-bound date.
  limit: 56, # Integer | 
  next_page_token: 'next_page_token_example' # String | Cursor returned by the previous call.
}

begin
  # Structured search across connected mail accounts.
  result = api_instance.search_emails(q, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->search_emails: #{e}"
end
```

#### Using the search_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchEmailsResponse>, Integer, Hash)> search_emails_with_http_info(q, opts)

```ruby
begin
  # Structured search across connected mail accounts.
  data, status_code, headers = api_instance.search_emails_with_http_info(q, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchEmailsResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->search_emails_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **q** | **String** | Provider-specific full-text query string. |  |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these connected-account row ids. Mutually orthogonal to &#x60;providers&#x60; — when both are set the intersection is used.  | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to these provider ids (&#x60;gmail&#x60;, &#x60;outlook&#x60;). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **from** | **String** |  | [optional] |
| **to** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **has_attachment** | **Boolean** |  | [optional] |
| **is_unread** | **Boolean** |  | [optional] |
| **is_starred** | **Boolean** |  | [optional] |
| **labels** | [**Array&lt;String&gt;**](String.md) |  | [optional] |
| **after** | **Time** | Inclusive lower-bound date. | [optional] |
| **before** | **Time** | Inclusive upper-bound date. | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **next_page_token** | **String** | Cursor returned by the previous call. | [optional] |

### Return type

[**SearchEmailsResponse**](SearchEmailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_draft

> <SendEmailResponse> send_draft(id, opts)

Send a draft.

Submits the draft as an outbound message. The draft is consumed by the provider — subsequent `getDraft`/`updateDraft` calls return `404`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Draft id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Send a draft.
  result = api_instance.send_draft(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->send_draft: #{e}"
end
```

#### Using the send_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailResponse>, Integer, Hash)> send_draft_with_http_info(id, opts)

```ruby
begin
  # Send a draft.
  data, status_code, headers = api_instance.send_draft_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->send_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Draft id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_email

> <SendEmailResponse> send_email(send_email_request, opts)

Send an email.

Sends through the resolved connected account (auto-picks if the caller has exactly one connected mail account; errors `ambiguous_account` otherwise unless `accountId` is supplied). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
send_email_request = Spatio::SendEmailRequest.new({to: ['to_example'], subject: 'subject_example', body: 'body_example'}) # SendEmailRequest | 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Send an email.
  result = api_instance.send_email(send_email_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->send_email: #{e}"
end
```

#### Using the send_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailResponse>, Integer, Hash)> send_email_with_http_info(send_email_request, opts)

```ruby
begin
  # Send an email.
  data, status_code, headers = api_instance.send_email_with_http_info(send_email_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->send_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **send_email_request** | [**SendEmailRequest**](SendEmailRequest.md) |  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SendEmailResponse**](SendEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_draft

> <DraftResponse> update_draft(id, update_draft_request, opts)

Update a draft (full replacement of provided fields).

PUT replaces the full set of provided fields on the draft. Fields omitted from the body are not modified. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Draft id.
update_draft_request = Spatio::UpdateDraftRequest.new # UpdateDraftRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a draft (full replacement of provided fields).
  result = api_instance.update_draft(id, update_draft_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_draft: #{e}"
end
```

#### Using the update_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DraftResponse>, Integer, Hash)> update_draft_with_http_info(id, update_draft_request, opts)

```ruby
begin
  # Update a draft (full replacement of provided fields).
  data, status_code, headers = api_instance.update_draft_with_http_info(id, update_draft_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DraftResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Draft id. |  |
| **update_draft_request** | [**UpdateDraftRequest**](UpdateDraftRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**DraftResponse**](DraftResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_email

> <UpdateEmailResponse> update_email(id, update_email_request, opts)

Update an email (mark read/star, add/remove labels).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | Email message id.
update_email_request = Spatio::UpdateEmailRequest.new # UpdateEmailRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update an email (mark read/star, add/remove labels).
  result = api_instance.update_email(id, update_email_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_email: #{e}"
end
```

#### Using the update_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateEmailResponse>, Integer, Hash)> update_email_with_http_info(id, update_email_request, opts)

```ruby
begin
  # Update an email (mark read/star, add/remove labels).
  data, status_code, headers = api_instance.update_email_with_http_info(id, update_email_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateEmailResponse>
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Email message id. |  |
| **update_email_request** | [**UpdateEmailRequest**](UpdateEmailRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**UpdateEmailResponse**](UpdateEmailResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_mail_template

> Hash&lt;String, Object&gt; update_mail_template(id, request_body)

Update a mail template.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Update a mail template.
  result = api_instance.update_mail_template(id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_mail_template: #{e}"
end
```

#### Using the update_mail_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_mail_template_with_http_info(id, request_body)

```ruby
begin
  # Update a mail template.
  data, status_code, headers = api_instance.update_mail_template_with_http_info(id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->update_mail_template_with_http_info: #{e}"
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


## workspace_add_mail_message_labels

> Hash&lt;String, Object&gt; workspace_add_mail_message_labels(org, workspace, message_id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
message_id = 'message_id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_add_mail_message_labels(org, workspace, message_id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_add_mail_message_labels: #{e}"
end
```

#### Using the workspace_add_mail_message_labels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_add_mail_message_labels_with_http_info(org, workspace, message_id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_add_mail_message_labels_with_http_info(org, workspace, message_id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_add_mail_message_labels_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **message_id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_mail_draft

> Hash&lt;String, Object&gt; workspace_create_mail_draft(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_mail_draft(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_create_mail_draft: #{e}"
end
```

#### Using the workspace_create_mail_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_mail_draft_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_mail_draft_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_create_mail_draft_with_http_info: #{e}"
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


## workspace_create_mail_label

> Hash&lt;String, Object&gt; workspace_create_mail_label(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_mail_label(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_create_mail_label: #{e}"
end
```

#### Using the workspace_create_mail_label_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_mail_label_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_mail_label_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_create_mail_label_with_http_info: #{e}"
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


## workspace_delete_mail

> workspace_delete_mail(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_mail(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail: #{e}"
end
```

#### Using the workspace_delete_mail_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_mail_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_mail_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail_with_http_info: #{e}"
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


## workspace_delete_mail_draft

> workspace_delete_mail_draft(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_mail_draft(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail_draft: #{e}"
end
```

#### Using the workspace_delete_mail_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_mail_draft_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_mail_draft_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail_draft_with_http_info: #{e}"
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


## workspace_delete_mail_label

> workspace_delete_mail_label(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_mail_label(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail_label: #{e}"
end
```

#### Using the workspace_delete_mail_label_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_mail_label_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_mail_label_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_delete_mail_label_with_http_info: #{e}"
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


## workspace_get_mail

> Hash&lt;String, Object&gt; workspace_get_mail(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_mail(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail: #{e}"
end
```

#### Using the workspace_get_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_mail_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_mail_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_with_http_info: #{e}"
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


## workspace_get_mail_attachment

> Hash&lt;String, Object&gt; workspace_get_mail_attachment(org, workspace, message_id, attachment_id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
message_id = 'message_id_example' # String | 
attachment_id = 'attachment_id_example' # String | 

begin
  
  result = api_instance.workspace_get_mail_attachment(org, workspace, message_id, attachment_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_attachment: #{e}"
end
```

#### Using the workspace_get_mail_attachment_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_mail_attachment_with_http_info(org, workspace, message_id, attachment_id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_mail_attachment_with_http_info(org, workspace, message_id, attachment_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_attachment_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **message_id** | **String** |  |  |
| **attachment_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_get_mail_by_id

> Hash&lt;String, Object&gt; workspace_get_mail_by_id(org, workspace, id)

Workspace-scoped renderer-compat alias for mail/email/{id}.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  # Workspace-scoped renderer-compat alias for mail/email/{id}.
  result = api_instance.workspace_get_mail_by_id(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_by_id: #{e}"
end
```

#### Using the workspace_get_mail_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_mail_by_id_with_http_info(org, workspace, id)

```ruby
begin
  # Workspace-scoped renderer-compat alias for mail/email/{id}.
  data, status_code, headers = api_instance.workspace_get_mail_by_id_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_by_id_with_http_info: #{e}"
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


## workspace_get_mail_draft

> Hash&lt;String, Object&gt; workspace_get_mail_draft(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_mail_draft(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_draft: #{e}"
end
```

#### Using the workspace_get_mail_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_mail_draft_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_mail_draft_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_draft_with_http_info: #{e}"
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


## workspace_get_mail_thread

> Hash&lt;String, Object&gt; workspace_get_mail_thread(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_mail_thread(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_thread: #{e}"
end
```

#### Using the workspace_get_mail_thread_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_mail_thread_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_mail_thread_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_get_mail_thread_with_http_info: #{e}"
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


## workspace_list_mail

> Hash&lt;String, Object&gt; workspace_list_mail(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_mail(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail: #{e}"
end
```

#### Using the workspace_list_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_mail_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_mail_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail_with_http_info: #{e}"
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


## workspace_list_mail_drafts

> Hash&lt;String, Object&gt; workspace_list_mail_drafts(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_mail_drafts(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail_drafts: #{e}"
end
```

#### Using the workspace_list_mail_drafts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_mail_drafts_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_mail_drafts_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail_drafts_with_http_info: #{e}"
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


## workspace_list_mail_labels

> Hash&lt;String, Object&gt; workspace_list_mail_labels(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_mail_labels(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail_labels: #{e}"
end
```

#### Using the workspace_list_mail_labels_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_mail_labels_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_mail_labels_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_list_mail_labels_with_http_info: #{e}"
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


## workspace_patch_mail

> Hash&lt;String, Object&gt; workspace_patch_mail(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_patch_mail(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_patch_mail: #{e}"
end
```

#### Using the workspace_patch_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_patch_mail_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_patch_mail_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_patch_mail_with_http_info: #{e}"
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


## workspace_remove_mail_message_label

> workspace_remove_mail_message_label(org, workspace, message_id, label_id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
message_id = 'message_id_example' # String | 
label_id = 'label_id_example' # String | 

begin
  
  api_instance.workspace_remove_mail_message_label(org, workspace, message_id, label_id)
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_remove_mail_message_label: #{e}"
end
```

#### Using the workspace_remove_mail_message_label_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_remove_mail_message_label_with_http_info(org, workspace, message_id, label_id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_remove_mail_message_label_with_http_info(org, workspace, message_id, label_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_remove_mail_message_label_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **message_id** | **String** |  |  |
| **label_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_reply_mail

> Hash&lt;String, Object&gt; workspace_reply_mail(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_reply_mail(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_reply_mail: #{e}"
end
```

#### Using the workspace_reply_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_reply_mail_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_reply_mail_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_reply_mail_with_http_info: #{e}"
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


## workspace_search_mail

> Hash&lt;String, Object&gt; workspace_search_mail(org, workspace, opts)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
opts = {
  q: 'q_example' # String | 
}

begin
  
  result = api_instance.workspace_search_mail(org, workspace, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_search_mail: #{e}"
end
```

#### Using the workspace_search_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_search_mail_with_http_info(org, workspace, opts)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_search_mail_with_http_info(org, workspace, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_search_mail_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **q** | **String** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_send_mail

> Hash&lt;String, Object&gt; workspace_send_mail(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_send_mail(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail: #{e}"
end
```

#### Using the workspace_send_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_send_mail_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_send_mail_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail_with_http_info: #{e}"
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


## workspace_send_mail_draft

> Hash&lt;String, Object&gt; workspace_send_mail_draft(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_send_mail_draft(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail_draft: #{e}"
end
```

#### Using the workspace_send_mail_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_send_mail_draft_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_send_mail_draft_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail_draft_with_http_info: #{e}"
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


## workspace_send_mail_email_alias

> Hash&lt;String, Object&gt; workspace_send_mail_email_alias(org, workspace, request_body)

Renderer-compat alias for /mail/send.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Renderer-compat alias for /mail/send.
  result = api_instance.workspace_send_mail_email_alias(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail_email_alias: #{e}"
end
```

#### Using the workspace_send_mail_email_alias_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_send_mail_email_alias_with_http_info(org, workspace, request_body)

```ruby
begin
  # Renderer-compat alias for /mail/send.
  data, status_code, headers = api_instance.workspace_send_mail_email_alias_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_send_mail_email_alias_with_http_info: #{e}"
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


## workspace_update_mail

> Hash&lt;String, Object&gt; workspace_update_mail(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_mail(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail: #{e}"
end
```

#### Using the workspace_update_mail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_mail_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_mail_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail_with_http_info: #{e}"
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


## workspace_update_mail_draft

> Hash&lt;String, Object&gt; workspace_update_mail_draft(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_mail_draft(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail_draft: #{e}"
end
```

#### Using the workspace_update_mail_draft_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_mail_draft_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_mail_draft_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail_draft_with_http_info: #{e}"
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


## workspace_update_mail_label

> Hash&lt;String, Object&gt; workspace_update_mail_label(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::MailApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_mail_label(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail_label: #{e}"
end
```

#### Using the workspace_update_mail_label_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_mail_label_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_mail_label_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling MailApi->workspace_update_mail_label_with_http_info: #{e}"
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

