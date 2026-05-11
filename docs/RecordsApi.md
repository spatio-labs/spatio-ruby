# Spatio::RecordsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_record**](RecordsApi.md#create_record) | **POST** /v1/records | Create a record. |
| [**create_record_type**](RecordsApi.md#create_record_type) | **POST** /v1/records/types | Create a record type (org-scoped). |
| [**delete_record**](RecordsApi.md#delete_record) | **DELETE** /v1/records/{id} | Delete a record. |
| [**get_record**](RecordsApi.md#get_record) | **GET** /v1/records/{id} | Fetch a record. |
| [**list_record_types**](RecordsApi.md#list_record_types) | **GET** /v1/records/types | List record types for an organization. |
| [**list_records**](RecordsApi.md#list_records) | **GET** /v1/records | List records for an organization. &#x60;organization_id&#x60; query param is required (handler returns 400 otherwise).  |
| [**update_record**](RecordsApi.md#update_record) | **PATCH** /v1/records/{id} | Update a record. |
| [**update_record_type**](RecordsApi.md#update_record_type) | **PATCH** /v1/records/types/{id} | Update a record type. |


## create_record

> <Record> create_record(create_record_request)

Create a record.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
create_record_request = Spatio::CreateRecordRequest.new({record_type_id: 'record_type_id_example'}) # CreateRecordRequest | 

begin
  # Create a record.
  result = api_instance.create_record(create_record_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->create_record: #{e}"
end
```

#### Using the create_record_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Record>, Integer, Hash)> create_record_with_http_info(create_record_request)

```ruby
begin
  # Create a record.
  data, status_code, headers = api_instance.create_record_with_http_info(create_record_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Record>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->create_record_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_record_request** | [**CreateRecordRequest**](CreateRecordRequest.md) |  |  |

### Return type

[**Record**](Record.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_record_type

> <RecordType> create_record_type(create_record_type_request)

Create a record type (org-scoped).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
create_record_type_request = Spatio::CreateRecordTypeRequest.new({name: 'name_example'}) # CreateRecordTypeRequest | 

begin
  # Create a record type (org-scoped).
  result = api_instance.create_record_type(create_record_type_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->create_record_type: #{e}"
end
```

#### Using the create_record_type_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecordType>, Integer, Hash)> create_record_type_with_http_info(create_record_type_request)

```ruby
begin
  # Create a record type (org-scoped).
  data, status_code, headers = api_instance.create_record_type_with_http_info(create_record_type_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecordType>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->create_record_type_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_record_type_request** | [**CreateRecordTypeRequest**](CreateRecordTypeRequest.md) |  |  |

### Return type

[**RecordType**](RecordType.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_record

> delete_record(id)

Delete a record.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
id = 'id_example' # String | 

begin
  # Delete a record.
  api_instance.delete_record(id)
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->delete_record: #{e}"
end
```

#### Using the delete_record_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_record_with_http_info(id)

```ruby
begin
  # Delete a record.
  data, status_code, headers = api_instance.delete_record_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->delete_record_with_http_info: #{e}"
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


## get_record

> <Record> get_record(id)

Fetch a record.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
id = 'id_example' # String | 

begin
  # Fetch a record.
  result = api_instance.get_record(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->get_record: #{e}"
end
```

#### Using the get_record_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Record>, Integer, Hash)> get_record_with_http_info(id)

```ruby
begin
  # Fetch a record.
  data, status_code, headers = api_instance.get_record_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Record>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->get_record_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Record**](Record.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_record_types

> <RecordTypeListResponse> list_record_types(organization_id)

List record types for an organization.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
organization_id = 'organization_id_example' # String | 

begin
  # List record types for an organization.
  result = api_instance.list_record_types(organization_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->list_record_types: #{e}"
end
```

#### Using the list_record_types_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecordTypeListResponse>, Integer, Hash)> list_record_types_with_http_info(organization_id)

```ruby
begin
  # List record types for an organization.
  data, status_code, headers = api_instance.list_record_types_with_http_info(organization_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecordTypeListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->list_record_types_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **organization_id** | **String** |  |  |

### Return type

[**RecordTypeListResponse**](RecordTypeListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_records

> <RecordListResponse> list_records(organization_id, opts)

List records for an organization. `organization_id` query param is required (handler returns 400 otherwise). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
organization_id = 'organization_id_example' # String | 
opts = {
  record_type_id: 'record_type_id_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List records for an organization. `organization_id` query param is required (handler returns 400 otherwise). 
  result = api_instance.list_records(organization_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->list_records: #{e}"
end
```

#### Using the list_records_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecordListResponse>, Integer, Hash)> list_records_with_http_info(organization_id, opts)

```ruby
begin
  # List records for an organization. `organization_id` query param is required (handler returns 400 otherwise). 
  data, status_code, headers = api_instance.list_records_with_http_info(organization_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecordListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->list_records_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **organization_id** | **String** |  |  |
| **record_type_id** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**RecordListResponse**](RecordListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_record

> <Record> update_record(id, update_record_request)

Update a record.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
id = 'id_example' # String | 
update_record_request = Spatio::UpdateRecordRequest.new # UpdateRecordRequest | 

begin
  # Update a record.
  result = api_instance.update_record(id, update_record_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->update_record: #{e}"
end
```

#### Using the update_record_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Record>, Integer, Hash)> update_record_with_http_info(id, update_record_request)

```ruby
begin
  # Update a record.
  data, status_code, headers = api_instance.update_record_with_http_info(id, update_record_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Record>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->update_record_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_record_request** | [**UpdateRecordRequest**](UpdateRecordRequest.md) |  |  |

### Return type

[**Record**](Record.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_record_type

> <RecordType> update_record_type(id, update_record_type_request)

Update a record type.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecordsApi.new
id = 'id_example' # String | 
update_record_type_request = Spatio::UpdateRecordTypeRequest.new # UpdateRecordTypeRequest | 

begin
  # Update a record type.
  result = api_instance.update_record_type(id, update_record_type_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->update_record_type: #{e}"
end
```

#### Using the update_record_type_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecordType>, Integer, Hash)> update_record_type_with_http_info(id, update_record_type_request)

```ruby
begin
  # Update a record type.
  data, status_code, headers = api_instance.update_record_type_with_http_info(id, update_record_type_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecordType>
rescue Spatio::ApiError => e
  puts "Error when calling RecordsApi->update_record_type_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_record_type_request** | [**UpdateRecordTypeRequest**](UpdateRecordTypeRequest.md) |  |  |

### Return type

[**RecordType**](RecordType.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

