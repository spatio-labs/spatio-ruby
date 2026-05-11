# Spatio::FoldersApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_email_folder**](FoldersApi.md#create_email_folder) | **POST** /v1/folders | Create an email folder. |
| [**delete_email_folder**](FoldersApi.md#delete_email_folder) | **DELETE** /v1/folders/{id} | Delete an email folder. |
| [**list_email_folders**](FoldersApi.md#list_email_folders) | **GET** /v1/folders | List the caller&#39;s email folders. |
| [**list_folder_emails**](FoldersApi.md#list_folder_emails) | **GET** /v1/folders/{id}/emails | List emails inside a folder. |
| [**move_emails_to_folder**](FoldersApi.md#move_emails_to_folder) | **POST** /v1/folders/{id}/emails | Move emails into a folder. |
| [**update_email_folder**](FoldersApi.md#update_email_folder) | **PUT** /v1/folders/{id} | Update an email folder. |


## create_email_folder

> <EmailFolder> create_email_folder(create_email_folder_request)

Create an email folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new
create_email_folder_request = Spatio::CreateEmailFolderRequest.new({name: 'name_example'}) # CreateEmailFolderRequest | 

begin
  # Create an email folder.
  result = api_instance.create_email_folder(create_email_folder_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->create_email_folder: #{e}"
end
```

#### Using the create_email_folder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EmailFolder>, Integer, Hash)> create_email_folder_with_http_info(create_email_folder_request)

```ruby
begin
  # Create an email folder.
  data, status_code, headers = api_instance.create_email_folder_with_http_info(create_email_folder_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EmailFolder>
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->create_email_folder_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_email_folder_request** | [**CreateEmailFolderRequest**](CreateEmailFolderRequest.md) |  |  |

### Return type

[**EmailFolder**](EmailFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_email_folder

> delete_email_folder(id)

Delete an email folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new
id = 'id_example' # String | 

begin
  # Delete an email folder.
  api_instance.delete_email_folder(id)
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->delete_email_folder: #{e}"
end
```

#### Using the delete_email_folder_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_email_folder_with_http_info(id)

```ruby
begin
  # Delete an email folder.
  data, status_code, headers = api_instance.delete_email_folder_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->delete_email_folder_with_http_info: #{e}"
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


## list_email_folders

> <EmailFolderListResponse> list_email_folders

List the caller's email folders.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new

begin
  # List the caller's email folders.
  result = api_instance.list_email_folders
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->list_email_folders: #{e}"
end
```

#### Using the list_email_folders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EmailFolderListResponse>, Integer, Hash)> list_email_folders_with_http_info

```ruby
begin
  # List the caller's email folders.
  data, status_code, headers = api_instance.list_email_folders_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EmailFolderListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->list_email_folders_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**EmailFolderListResponse**](EmailFolderListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_folder_emails

> Hash&lt;String, Object&gt; list_folder_emails(id)

List emails inside a folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new
id = 'id_example' # String | 

begin
  # List emails inside a folder.
  result = api_instance.list_folder_emails(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->list_folder_emails: #{e}"
end
```

#### Using the list_folder_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_folder_emails_with_http_info(id)

```ruby
begin
  # List emails inside a folder.
  data, status_code, headers = api_instance.list_folder_emails_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->list_folder_emails_with_http_info: #{e}"
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


## move_emails_to_folder

> Hash&lt;String, Object&gt; move_emails_to_folder(id, move_emails_request)

Move emails into a folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new
id = 'id_example' # String | 
move_emails_request = Spatio::MoveEmailsRequest.new({message_ids: ['message_ids_example']}) # MoveEmailsRequest | 

begin
  # Move emails into a folder.
  result = api_instance.move_emails_to_folder(id, move_emails_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->move_emails_to_folder: #{e}"
end
```

#### Using the move_emails_to_folder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> move_emails_to_folder_with_http_info(id, move_emails_request)

```ruby
begin
  # Move emails into a folder.
  data, status_code, headers = api_instance.move_emails_to_folder_with_http_info(id, move_emails_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->move_emails_to_folder_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **move_emails_request** | [**MoveEmailsRequest**](MoveEmailsRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_email_folder

> <EmailFolder> update_email_folder(id, update_email_folder_request)

Update an email folder.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::FoldersApi.new
id = 'id_example' # String | 
update_email_folder_request = Spatio::UpdateEmailFolderRequest.new # UpdateEmailFolderRequest | 

begin
  # Update an email folder.
  result = api_instance.update_email_folder(id, update_email_folder_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->update_email_folder: #{e}"
end
```

#### Using the update_email_folder_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<EmailFolder>, Integer, Hash)> update_email_folder_with_http_info(id, update_email_folder_request)

```ruby
begin
  # Update an email folder.
  data, status_code, headers = api_instance.update_email_folder_with_http_info(id, update_email_folder_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <EmailFolder>
rescue Spatio::ApiError => e
  puts "Error when calling FoldersApi->update_email_folder_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_email_folder_request** | [**UpdateEmailFolderRequest**](UpdateEmailFolderRequest.md) |  |  |

### Return type

[**EmailFolder**](EmailFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

