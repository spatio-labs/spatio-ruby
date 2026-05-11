# Spatio::FilesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**bulk_delete_files**](FilesApi.md#bulk_delete_files) | **POST** /v1/files/delete | Delete multiple files in one call. |
| [**bulk_move_files**](FilesApi.md#bulk_move_files) | **POST** /v1/files/move | Move multiple files to a target folder. |
| [**commit_chunked_upload**](FilesApi.md#commit_chunked_upload) | **POST** /v1/files/upload/chunked/commit | Finalize a chunked-upload session and create the file row. |
| [**create_file_folder**](FilesApi.md#create_file_folder) | **POST** /v1/files/folders | Create a folder. |
| [**delete_file**](FilesApi.md#delete_file) | **DELETE** /v1/files/{id} | Delete a file. |
| [**extract_file_text**](FilesApi.md#extract_file_text) | **GET** /v1/files/{id}/extract-text | Extract text content from a PDF (or other supported file). |
| [**get_chunked_file_manifest**](FilesApi.md#get_chunked_file_manifest) | **GET** /v1/files/{id}/manifest | Fetch the block manifest for a chunked-uploaded file. |
| [**get_file**](FilesApi.md#get_file) | **GET** /v1/files/{id} | Fetch one file&#39;s metadata. |
| [**get_file_download_url**](FilesApi.md#get_file_download_url) | **GET** /v1/files/{id}/download | Mint a fresh signed download URL. |
| [**init_chunked_upload**](FilesApi.md#init_chunked_upload) | **POST** /v1/files/upload/chunked/init | Begin a content-addressed chunked upload session. |
| [**list_file_folders**](FilesApi.md#list_file_folders) | **GET** /v1/files/folders | List folders across connected file providers. |
| [**list_files**](FilesApi.md#list_files) | **GET** /v1/files | List files across connected file providers. |
| [**list_files_and_folders**](FilesApi.md#list_files_and_folders) | **GET** /v1/files/list | Aggregate list of files + folders for renderer file-browser views. |
| [**move_file**](FilesApi.md#move_file) | **POST** /v1/files/{id}/move | Move a single file to a target folder. |
| [**search_files**](FilesApi.md#search_files) | **GET** /v1/files/search | Substring-match search across the caller&#39;s files. |
| [**update_file**](FilesApi.md#update_file) | **PATCH** /v1/files/{id} | Update a file&#39;s metadata (name, folder, custom fields). |
| [**upload_chunked_block**](FilesApi.md#upload_chunked_block) | **POST** /v1/files/upload/chunked/blocks | Upload one block for an open chunked-upload session. |
| [**upload_file**](FilesApi.md#upload_file) | **POST** /v1/files/upload | Upload a file via multipart form. |
| [**upload_file_base64**](FilesApi.md#upload_file_base64) | **POST** /v1/files/upload/base64 | Upload a file via JSON with base64-encoded content. |
| [**workspace_commit_chunked_upload**](FilesApi.md#workspace_commit_chunked_upload) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/commit | Workspace-scoped chunked-upload commit (RBAC-protected). |
| [**workspace_create_file_folder**](FilesApi.md#workspace_create_file_folder) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/folders | Workspace-scoped create-folder (RBAC-protected). |
| [**workspace_delete_file**](FilesApi.md#workspace_delete_file) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped delete-file. |
| [**workspace_get_file**](FilesApi.md#workspace_get_file) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped get-file. |
| [**workspace_get_file_download**](FilesApi.md#workspace_get_file_download) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/download | Workspace-scoped signed-download URL. |
| [**workspace_get_file_manifest**](FilesApi.md#workspace_get_file_manifest) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/manifest | Workspace-scoped chunked-file manifest. |
| [**workspace_init_chunked_upload**](FilesApi.md#workspace_init_chunked_upload) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/init | Workspace-scoped chunked-upload init (RBAC-protected). |
| [**workspace_list_file_folders**](FilesApi.md#workspace_list_file_folders) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files/folders | Workspace-scoped list-folders (RBAC-protected). |
| [**workspace_list_files**](FilesApi.md#workspace_list_files) | **GET** /v1/organizations/{org}/workspaces/{workspace}/files | Workspace-scoped list-files (RBAC-protected). |
| [**workspace_move_file**](FilesApi.md#workspace_move_file) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/{id}/move | Workspace-scoped move-file. |
| [**workspace_update_file**](FilesApi.md#workspace_update_file) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/files/{id} | Workspace-scoped update-file. |
| [**workspace_upload_chunked_block**](FilesApi.md#workspace_upload_chunked_block) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/chunked/blocks | Workspace-scoped chunked-upload block (RBAC-protected). |
| [**workspace_upload_file**](FilesApi.md#workspace_upload_file) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload | Workspace-scoped multipart upload (RBAC-protected). |
| [**workspace_upload_file_base64**](FilesApi.md#workspace_upload_file_base64) | **POST** /v1/organizations/{org}/workspaces/{workspace}/files/upload/base64 | Workspace-scoped base64 upload (RBAC-protected). |


## bulk_delete_files

> <BulkFilesResponse> bulk_delete_files(bulk_delete_files_request)

Delete multiple files in one call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
bulk_delete_files_request = Spatio::BulkDeleteFilesRequest.new # BulkDeleteFilesRequest | 

begin
  # Delete multiple files in one call.
  result = api_instance.bulk_delete_files(bulk_delete_files_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->bulk_delete_files: #{e}"
end
```

#### Using the bulk_delete_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkFilesResponse>, Integer, Hash)> bulk_delete_files_with_http_info(bulk_delete_files_request)

```ruby
begin
  # Delete multiple files in one call.
  data, status_code, headers = api_instance.bulk_delete_files_with_http_info(bulk_delete_files_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkFilesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->bulk_delete_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_delete_files_request** | [**BulkDeleteFilesRequest**](BulkDeleteFilesRequest.md) |  |  |

### Return type

[**BulkFilesResponse**](BulkFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## bulk_move_files

> <BulkFilesResponse> bulk_move_files(bulk_move_files_request)

Move multiple files to a target folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
bulk_move_files_request = Spatio::BulkMoveFilesRequest.new # BulkMoveFilesRequest | 

begin
  # Move multiple files to a target folder.
  result = api_instance.bulk_move_files(bulk_move_files_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->bulk_move_files: #{e}"
end
```

#### Using the bulk_move_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BulkFilesResponse>, Integer, Hash)> bulk_move_files_with_http_info(bulk_move_files_request)

```ruby
begin
  # Move multiple files to a target folder.
  data, status_code, headers = api_instance.bulk_move_files_with_http_info(bulk_move_files_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BulkFilesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->bulk_move_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bulk_move_files_request** | [**BulkMoveFilesRequest**](BulkMoveFilesRequest.md) |  |  |

### Return type

[**BulkFilesResponse**](BulkFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## commit_chunked_upload

> <CommitChunkedUploadResponse> commit_chunked_upload(commit_chunked_upload_request)

Finalize a chunked-upload session and create the file row.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
commit_chunked_upload_request = Spatio::CommitChunkedUploadRequest.new({session_id: 'session_id_example'}) # CommitChunkedUploadRequest | 

begin
  # Finalize a chunked-upload session and create the file row.
  result = api_instance.commit_chunked_upload(commit_chunked_upload_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->commit_chunked_upload: #{e}"
end
```

#### Using the commit_chunked_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CommitChunkedUploadResponse>, Integer, Hash)> commit_chunked_upload_with_http_info(commit_chunked_upload_request)

```ruby
begin
  # Finalize a chunked-upload session and create the file row.
  data, status_code, headers = api_instance.commit_chunked_upload_with_http_info(commit_chunked_upload_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CommitChunkedUploadResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->commit_chunked_upload_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **commit_chunked_upload_request** | [**CommitChunkedUploadRequest**](CommitChunkedUploadRequest.md) |  |  |

### Return type

[**CommitChunkedUploadResponse**](CommitChunkedUploadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_file_folder

> <Folder> create_file_folder(create_folder_request, opts)

Create a folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
create_folder_request = Spatio::CreateFolderRequest.new({name: 'name_example'}) # CreateFolderRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a folder.
  result = api_instance.create_file_folder(create_folder_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->create_file_folder: #{e}"
end
```

#### Using the create_file_folder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Folder>, Integer, Hash)> create_file_folder_with_http_info(create_folder_request, opts)

```ruby
begin
  # Create a folder.
  data, status_code, headers = api_instance.create_file_folder_with_http_info(create_folder_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Folder>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->create_file_folder_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_folder_request** | [**CreateFolderRequest**](CreateFolderRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Folder**](Folder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_file

> delete_file(id, opts)

Delete a file.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a file.
  api_instance.delete_file(id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->delete_file: #{e}"
end
```

#### Using the delete_file_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_file_with_http_info(id, opts)

```ruby
begin
  # Delete a file.
  data, status_code, headers = api_instance.delete_file_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->delete_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## extract_file_text

> <ExtractTextResult> extract_file_text(id, opts)

Extract text content from a PDF (or other supported file).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  page_start: 56, # Integer | 
  page_end: 56, # Integer | 
  max_chars: 56 # Integer | Truncation limit; sets `truncated: true` when hit.
}

begin
  # Extract text content from a PDF (or other supported file).
  result = api_instance.extract_file_text(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->extract_file_text: #{e}"
end
```

#### Using the extract_file_text_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExtractTextResult>, Integer, Hash)> extract_file_text_with_http_info(id, opts)

```ruby
begin
  # Extract text content from a PDF (or other supported file).
  data, status_code, headers = api_instance.extract_file_text_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExtractTextResult>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->extract_file_text_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **page_start** | **Integer** |  | [optional] |
| **page_end** | **Integer** |  | [optional] |
| **max_chars** | **Integer** | Truncation limit; sets &#x60;truncated: true&#x60; when hit. | [optional] |

### Return type

[**ExtractTextResult**](ExtractTextResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_chunked_file_manifest

> <ChunkedFileManifest> get_chunked_file_manifest(id, opts)

Fetch the block manifest for a chunked-uploaded file.

Only meaningful for files uploaded via `upload/chunked/*`. Files uploaded via `upload` or `upload/base64` return `404`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch the block manifest for a chunked-uploaded file.
  result = api_instance.get_chunked_file_manifest(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_chunked_file_manifest: #{e}"
end
```

#### Using the get_chunked_file_manifest_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ChunkedFileManifest>, Integer, Hash)> get_chunked_file_manifest_with_http_info(id, opts)

```ruby
begin
  # Fetch the block manifest for a chunked-uploaded file.
  data, status_code, headers = api_instance.get_chunked_file_manifest_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ChunkedFileManifest>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_chunked_file_manifest_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ChunkedFileManifest**](ChunkedFileManifest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_file

> <SpatioFile> get_file(id, opts)

Fetch one file's metadata.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one file's metadata.
  result = api_instance.get_file(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_file: #{e}"
end
```

#### Using the get_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioFile>, Integer, Hash)> get_file_with_http_info(id, opts)

```ruby
begin
  # Fetch one file's metadata.
  data, status_code, headers = api_instance.get_file_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioFile>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_file_download_url

> <DownloadFileResponse> get_file_download_url(id, opts)

Mint a fresh signed download URL.

Returns a JSON envelope with a pre-signed URL pointing at the backing storage. Clients follow the URL — the platform does not stream bytes through itself. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Mint a fresh signed download URL.
  result = api_instance.get_file_download_url(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_file_download_url: #{e}"
end
```

#### Using the get_file_download_url_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DownloadFileResponse>, Integer, Hash)> get_file_download_url_with_http_info(id, opts)

```ruby
begin
  # Mint a fresh signed download URL.
  data, status_code, headers = api_instance.get_file_download_url_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DownloadFileResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->get_file_download_url_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**DownloadFileResponse**](DownloadFileResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## init_chunked_upload

> <InitChunkedUploadResponse> init_chunked_upload(init_chunked_upload_request)

Begin a content-addressed chunked upload session.

Client computes per-block hashes ahead of time and submits the list. The server replies with which blocks need uploading vs. already-on-server (deduplicated). Subsequent calls upload the missing blocks via `uploadChunkedBlock`, then `commit`. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
init_chunked_upload_request = Spatio::InitChunkedUploadRequest.new({file_name: 'file_name_example', total_size: 3.56, mime_type: 'mime_type_example', expected_blocks: ['expected_blocks_example']}) # InitChunkedUploadRequest | 

begin
  # Begin a content-addressed chunked upload session.
  result = api_instance.init_chunked_upload(init_chunked_upload_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->init_chunked_upload: #{e}"
end
```

#### Using the init_chunked_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<InitChunkedUploadResponse>, Integer, Hash)> init_chunked_upload_with_http_info(init_chunked_upload_request)

```ruby
begin
  # Begin a content-addressed chunked upload session.
  data, status_code, headers = api_instance.init_chunked_upload_with_http_info(init_chunked_upload_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <InitChunkedUploadResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->init_chunked_upload_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **init_chunked_upload_request** | [**InitChunkedUploadRequest**](InitChunkedUploadRequest.md) |  |  |

### Return type

[**InitChunkedUploadResponse**](InitChunkedUploadResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_file_folders

> <FolderListEnvelope> list_file_folders(opts)

List folders across connected file providers.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  parent_id: 'parent_id_example', # String | Filter to children of this folder. Omit for root.
  workspace_id: 'workspace_id_example', # String | 
  organization_id: 'organization_id_example', # String | 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List folders across connected file providers.
  result = api_instance.list_file_folders(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_file_folders: #{e}"
end
```

#### Using the list_file_folders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FolderListEnvelope>, Integer, Hash)> list_file_folders_with_http_info(opts)

```ruby
begin
  # List folders across connected file providers.
  data, status_code, headers = api_instance.list_file_folders_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FolderListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_file_folders_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **parent_id** | **String** | Filter to children of this folder. Omit for root. | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**FolderListEnvelope**](FolderListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_files

> <FileListEnvelope> list_files(opts)

List files across connected file providers.

Fan-out list. Returns files from every connected file provider unless filtered by `?accountId=` or `?provider=`. Folder contents are scoped via `?folderId=`; omit for account root. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  folder_id: 'folder_id_example', # String | Filter to one folder. Omit for the account root.
  workspace_id: 'workspace_id_example', # String | 
  organization_id: 'organization_id_example', # String | 
  limit: 56, # Integer | 
  offset: 56, # Integer | 
  sort_by: 'sort_by_example', # String | Provider-dependent. Common values: `created_at`, `name`, `size`.
  sort_order: 'ASC' # String | 
}

begin
  # List files across connected file providers.
  result = api_instance.list_files(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_files: #{e}"
end
```

#### Using the list_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FileListEnvelope>, Integer, Hash)> list_files_with_http_info(opts)

```ruby
begin
  # List files across connected file providers.
  data, status_code, headers = api_instance.list_files_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FileListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **folder_id** | **String** | Filter to one folder. Omit for the account root. | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |
| **sort_by** | **String** | Provider-dependent. Common values: &#x60;created_at&#x60;, &#x60;name&#x60;, &#x60;size&#x60;. | [optional][default to &#39;created_at&#39;] |
| **sort_order** | **String** |  | [optional][default to &#39;DESC&#39;] |

### Return type

[**FileListEnvelope**](FileListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_files_and_folders

> <FilesAndFoldersResponse> list_files_and_folders(opts)

Aggregate list of files + folders for renderer file-browser views.

Calls `listFiles` and `listFileFolders` in parallel and merges the results. Saves a round-trip when the UI shows both side-by-side. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  folder_id: 'folder_id_example', # String | Filter to one folder. Omit for the account root.
  workspace_id: 'workspace_id_example', # String | 
  organization_id: 'organization_id_example', # String | 
  limit: 56, # Integer | 
  offset: 56, # Integer | 
  sort_by: 'sort_by_example', # String | 
  sort_order: 'sort_order_example' # String | 
}

begin
  # Aggregate list of files + folders for renderer file-browser views.
  result = api_instance.list_files_and_folders(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_files_and_folders: #{e}"
end
```

#### Using the list_files_and_folders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FilesAndFoldersResponse>, Integer, Hash)> list_files_and_folders_with_http_info(opts)

```ruby
begin
  # Aggregate list of files + folders for renderer file-browser views.
  data, status_code, headers = api_instance.list_files_and_folders_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FilesAndFoldersResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->list_files_and_folders_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **folder_id** | **String** | Filter to one folder. Omit for the account root. | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |
| **sort_by** | **String** |  | [optional] |
| **sort_order** | **String** |  | [optional] |

### Return type

[**FilesAndFoldersResponse**](FilesAndFoldersResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## move_file

> <MoveFileResponse> move_file(id, move_file_request, opts)

Move a single file to a target folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
move_file_request = Spatio::MoveFileRequest.new # MoveFileRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Move a single file to a target folder.
  result = api_instance.move_file(id, move_file_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->move_file: #{e}"
end
```

#### Using the move_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MoveFileResponse>, Integer, Hash)> move_file_with_http_info(id, move_file_request, opts)

```ruby
begin
  # Move a single file to a target folder.
  data, status_code, headers = api_instance.move_file_with_http_info(id, move_file_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MoveFileResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->move_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **move_file_request** | [**MoveFileRequest**](MoveFileRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**MoveFileResponse**](MoveFileResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## search_files

> <SearchFilesResponse> search_files(query, opts)

Substring-match search across the caller's files.

In-memory search — the platform lists up to ~500 files and filters locally on `name` (case-insensitive substring). Not suitable for global search across very large file libraries. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
query = 'query_example' # String | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  folder_id: 'folder_id_example', # String | Filter to one folder. Omit for the account root.
  workspace_id: 'workspace_id_example', # String | 
  organization_id: 'organization_id_example', # String | 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # Substring-match search across the caller's files.
  result = api_instance.search_files(query, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->search_files: #{e}"
end
```

#### Using the search_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchFilesResponse>, Integer, Hash)> search_files_with_http_info(query, opts)

```ruby
begin
  # Substring-match search across the caller's files.
  data, status_code, headers = api_instance.search_files_with_http_info(query, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchFilesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->search_files_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query** | **String** |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **folder_id** | **String** | Filter to one folder. Omit for the account root. | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**SearchFilesResponse**](SearchFilesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_file

> <SpatioFile> update_file(id, update_file_request, opts)

Update a file's metadata (name, folder, custom fields).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
id = 'id_example' # String | File id.
update_file_request = Spatio::UpdateFileRequest.new # UpdateFileRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a file's metadata (name, folder, custom fields).
  result = api_instance.update_file(id, update_file_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->update_file: #{e}"
end
```

#### Using the update_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioFile>, Integer, Hash)> update_file_with_http_info(id, update_file_request, opts)

```ruby
begin
  # Update a file's metadata (name, folder, custom fields).
  data, status_code, headers = api_instance.update_file_with_http_info(id, update_file_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioFile>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->update_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | File id. |  |
| **update_file_request** | [**UpdateFileRequest**](UpdateFileRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## upload_chunked_block

> <UploadChunkedBlockResponse> upload_chunked_block(session_id, block_hash, block, opts)

Upload one block for an open chunked-upload session.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
session_id = 'session_id_example' # String | 
block_hash = 'block_hash_example' # String | 
block = File.new('/path/to/some/file') # File | 
opts = {
  block_index: 56 # Integer | 
}

begin
  # Upload one block for an open chunked-upload session.
  result = api_instance.upload_chunked_block(session_id, block_hash, block, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_chunked_block: #{e}"
end
```

#### Using the upload_chunked_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UploadChunkedBlockResponse>, Integer, Hash)> upload_chunked_block_with_http_info(session_id, block_hash, block, opts)

```ruby
begin
  # Upload one block for an open chunked-upload session.
  data, status_code, headers = api_instance.upload_chunked_block_with_http_info(session_id, block_hash, block, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UploadChunkedBlockResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_chunked_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **session_id** | **String** |  |  |
| **block_hash** | **String** |  |  |
| **block** | **File** |  |  |
| **block_index** | **Integer** |  | [optional] |

### Return type

[**UploadChunkedBlockResponse**](UploadChunkedBlockResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json


## upload_file

> <SpatioFile> upload_file(file, opts)

Upload a file via multipart form.

Multipart upload. Form field `file` carries the binary; auxiliary form fields scope the upload (`folderId`, `workspaceId`, `organizationId`, `accountId`). Max body size is currently 100 MB. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
file = File.new('/path/to/some/file') # File | File bytes (multipart form field name `file`).
opts = {
  folder_id: 'folder_id_example', # String | 
  workspace_id: 'workspace_id_example', # String | 
  organization_id: 'organization_id_example', # String | 
  account_id: 'account_id_example' # String | 
}

begin
  # Upload a file via multipart form.
  result = api_instance.upload_file(file, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_file: #{e}"
end
```

#### Using the upload_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioFile>, Integer, Hash)> upload_file_with_http_info(file, opts)

```ruby
begin
  # Upload a file via multipart form.
  data, status_code, headers = api_instance.upload_file_with_http_info(file, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioFile>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file** | **File** | File bytes (multipart form field name &#x60;file&#x60;). |  |
| **folder_id** | **String** |  | [optional] |
| **workspace_id** | **String** |  | [optional] |
| **organization_id** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json


## upload_file_base64

> <SpatioFile> upload_file_base64(upload_file_base64_request)

Upload a file via JSON with base64-encoded content.

Equivalent to `uploadFile` for clients that can't post multipart bodies (e.g. browser fetch with strict CSP). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
upload_file_base64_request = Spatio::UploadFileBase64Request.new({name: 'name_example', content: 'content_example', mime_type: 'mime_type_example'}) # UploadFileBase64Request | 

begin
  # Upload a file via JSON with base64-encoded content.
  result = api_instance.upload_file_base64(upload_file_base64_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_file_base64: #{e}"
end
```

#### Using the upload_file_base64_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioFile>, Integer, Hash)> upload_file_base64_with_http_info(upload_file_base64_request)

```ruby
begin
  # Upload a file via JSON with base64-encoded content.
  data, status_code, headers = api_instance.upload_file_base64_with_http_info(upload_file_base64_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioFile>
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->upload_file_base64_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **upload_file_base64_request** | [**UploadFileBase64Request**](UploadFileBase64Request.md) |  |  |

### Return type

[**SpatioFile**](SpatioFile.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_commit_chunked_upload

> Hash&lt;String, Object&gt; workspace_commit_chunked_upload(org, workspace, request_body)

Workspace-scoped chunked-upload commit (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped chunked-upload commit (RBAC-protected).
  result = api_instance.workspace_commit_chunked_upload(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_commit_chunked_upload: #{e}"
end
```

#### Using the workspace_commit_chunked_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_commit_chunked_upload_with_http_info(org, workspace, request_body)

```ruby
begin
  # Workspace-scoped chunked-upload commit (RBAC-protected).
  data, status_code, headers = api_instance.workspace_commit_chunked_upload_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_commit_chunked_upload_with_http_info: #{e}"
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


## workspace_create_file_folder

> Hash&lt;String, Object&gt; workspace_create_file_folder(org, workspace, request_body)

Workspace-scoped create-folder (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped create-folder (RBAC-protected).
  result = api_instance.workspace_create_file_folder(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_create_file_folder: #{e}"
end
```

#### Using the workspace_create_file_folder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_file_folder_with_http_info(org, workspace, request_body)

```ruby
begin
  # Workspace-scoped create-folder (RBAC-protected).
  data, status_code, headers = api_instance.workspace_create_file_folder_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_create_file_folder_with_http_info: #{e}"
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


## workspace_delete_file

> workspace_delete_file(org, workspace, id)

Workspace-scoped delete-file.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  # Workspace-scoped delete-file.
  api_instance.workspace_delete_file(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_delete_file: #{e}"
end
```

#### Using the workspace_delete_file_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_file_with_http_info(org, workspace, id)

```ruby
begin
  # Workspace-scoped delete-file.
  data, status_code, headers = api_instance.workspace_delete_file_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_delete_file_with_http_info: #{e}"
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


## workspace_get_file

> Hash&lt;String, Object&gt; workspace_get_file(org, workspace, id)

Workspace-scoped get-file.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  # Workspace-scoped get-file.
  result = api_instance.workspace_get_file(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file: #{e}"
end
```

#### Using the workspace_get_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_file_with_http_info(org, workspace, id)

```ruby
begin
  # Workspace-scoped get-file.
  data, status_code, headers = api_instance.workspace_get_file_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file_with_http_info: #{e}"
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


## workspace_get_file_download

> Hash&lt;String, Object&gt; workspace_get_file_download(org, workspace, id)

Workspace-scoped signed-download URL.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  # Workspace-scoped signed-download URL.
  result = api_instance.workspace_get_file_download(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file_download: #{e}"
end
```

#### Using the workspace_get_file_download_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_file_download_with_http_info(org, workspace, id)

```ruby
begin
  # Workspace-scoped signed-download URL.
  data, status_code, headers = api_instance.workspace_get_file_download_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file_download_with_http_info: #{e}"
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


## workspace_get_file_manifest

> Hash&lt;String, Object&gt; workspace_get_file_manifest(org, workspace, id)

Workspace-scoped chunked-file manifest.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  # Workspace-scoped chunked-file manifest.
  result = api_instance.workspace_get_file_manifest(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file_manifest: #{e}"
end
```

#### Using the workspace_get_file_manifest_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_file_manifest_with_http_info(org, workspace, id)

```ruby
begin
  # Workspace-scoped chunked-file manifest.
  data, status_code, headers = api_instance.workspace_get_file_manifest_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_get_file_manifest_with_http_info: #{e}"
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


## workspace_init_chunked_upload

> Hash&lt;String, Object&gt; workspace_init_chunked_upload(org, workspace, request_body)

Workspace-scoped chunked-upload init (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped chunked-upload init (RBAC-protected).
  result = api_instance.workspace_init_chunked_upload(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_init_chunked_upload: #{e}"
end
```

#### Using the workspace_init_chunked_upload_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_init_chunked_upload_with_http_info(org, workspace, request_body)

```ruby
begin
  # Workspace-scoped chunked-upload init (RBAC-protected).
  data, status_code, headers = api_instance.workspace_init_chunked_upload_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_init_chunked_upload_with_http_info: #{e}"
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


## workspace_list_file_folders

> Hash&lt;String, Object&gt; workspace_list_file_folders(org, workspace)

Workspace-scoped list-folders (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  # Workspace-scoped list-folders (RBAC-protected).
  result = api_instance.workspace_list_file_folders(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_list_file_folders: #{e}"
end
```

#### Using the workspace_list_file_folders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_file_folders_with_http_info(org, workspace)

```ruby
begin
  # Workspace-scoped list-folders (RBAC-protected).
  data, status_code, headers = api_instance.workspace_list_file_folders_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_list_file_folders_with_http_info: #{e}"
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


## workspace_list_files

> Hash&lt;String, Object&gt; workspace_list_files(org, workspace)

Workspace-scoped list-files (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  # Workspace-scoped list-files (RBAC-protected).
  result = api_instance.workspace_list_files(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_list_files: #{e}"
end
```

#### Using the workspace_list_files_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_files_with_http_info(org, workspace)

```ruby
begin
  # Workspace-scoped list-files (RBAC-protected).
  data, status_code, headers = api_instance.workspace_list_files_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_list_files_with_http_info: #{e}"
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


## workspace_move_file

> Hash&lt;String, Object&gt; workspace_move_file(org, workspace, id, request_body)

Workspace-scoped move-file.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped move-file.
  result = api_instance.workspace_move_file(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_move_file: #{e}"
end
```

#### Using the workspace_move_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_move_file_with_http_info(org, workspace, id, request_body)

```ruby
begin
  # Workspace-scoped move-file.
  data, status_code, headers = api_instance.workspace_move_file_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_move_file_with_http_info: #{e}"
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


## workspace_update_file

> Hash&lt;String, Object&gt; workspace_update_file(org, workspace, id, request_body)

Workspace-scoped update-file.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped update-file.
  result = api_instance.workspace_update_file(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_update_file: #{e}"
end
```

#### Using the workspace_update_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_file_with_http_info(org, workspace, id, request_body)

```ruby
begin
  # Workspace-scoped update-file.
  data, status_code, headers = api_instance.workspace_update_file_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_update_file_with_http_info: #{e}"
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


## workspace_upload_chunked_block

> Hash&lt;String, Object&gt; workspace_upload_chunked_block(org, workspace, body)

Workspace-scoped chunked-upload block (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
body = File.new('/path/to/some/file') # File | 

begin
  # Workspace-scoped chunked-upload block (RBAC-protected).
  result = api_instance.workspace_upload_chunked_block(org, workspace, body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_chunked_block: #{e}"
end
```

#### Using the workspace_upload_chunked_block_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_upload_chunked_block_with_http_info(org, workspace, body)

```ruby
begin
  # Workspace-scoped chunked-upload block (RBAC-protected).
  data, status_code, headers = api_instance.workspace_upload_chunked_block_with_http_info(org, workspace, body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_chunked_block_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **body** | **File** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/octet-stream
- **Accept**: application/json


## workspace_upload_file

> Hash&lt;String, Object&gt; workspace_upload_file(org, workspace, opts)

Workspace-scoped multipart upload (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
opts = {
  file: File.new('/path/to/some/file') # File | 
}

begin
  # Workspace-scoped multipart upload (RBAC-protected).
  result = api_instance.workspace_upload_file(org, workspace, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_file: #{e}"
end
```

#### Using the workspace_upload_file_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_upload_file_with_http_info(org, workspace, opts)

```ruby
begin
  # Workspace-scoped multipart upload (RBAC-protected).
  data, status_code, headers = api_instance.workspace_upload_file_with_http_info(org, workspace, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **file** | **File** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json


## workspace_upload_file_base64

> Hash&lt;String, Object&gt; workspace_upload_file_base64(org, workspace, request_body)

Workspace-scoped base64 upload (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FilesApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped base64 upload (RBAC-protected).
  result = api_instance.workspace_upload_file_base64(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_file_base64: #{e}"
end
```

#### Using the workspace_upload_file_base64_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_upload_file_base64_with_http_info(org, workspace, request_body)

```ruby
begin
  # Workspace-scoped base64 upload (RBAC-protected).
  data, status_code, headers = api_instance.workspace_upload_file_base64_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FilesApi->workspace_upload_file_base64_with_http_info: #{e}"
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

