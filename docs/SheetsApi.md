# Spatio::SheetsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_sheet**](SheetsApi.md#create_sheet) | **POST** /v1/sheets | Create a sheet. |
| [**create_sheet_row**](SheetsApi.md#create_sheet_row) | **POST** /v1/sheets/{id}/rows | Insert a row. |
| [**delete_sheet**](SheetsApi.md#delete_sheet) | **DELETE** /v1/sheets/{id} | Delete a sheet. |
| [**delete_sheet_row**](SheetsApi.md#delete_sheet_row) | **DELETE** /v1/sheets/{id}/rows/{rowIndex} | Delete a row. |
| [**get_sheet**](SheetsApi.md#get_sheet) | **GET** /v1/sheets/{id} | Fetch one sheet. |
| [**list_sheet_rows**](SheetsApi.md#list_sheet_rows) | **GET** /v1/sheets/{id}/rows | List rows in a sheet. |
| [**list_sheets**](SheetsApi.md#list_sheets) | **GET** /v1/sheets | List sheets across connected accounts. |
| [**update_sheet**](SheetsApi.md#update_sheet) | **PATCH** /v1/sheets/{id} | Update a sheet (partial). |
| [**update_sheet_cell**](SheetsApi.md#update_sheet_cell) | **PATCH** /v1/sheets/{id}/rows/{rowIndex}/cells/{column} | Update a single cell. |
| [**update_sheet_row**](SheetsApi.md#update_sheet_row) | **PATCH** /v1/sheets/{id}/rows/{rowIndex} | Update a row (sparse). |


## create_sheet

> <Sheet> create_sheet(create_sheet_request, opts)

Create a sheet.

Creates a new sheet under the target account. Target resolution mirrors `POST /v1/notes`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors with `ambiguous_account` if more than one is connected and no selector is supplied). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
create_sheet_request = Spatio::CreateSheetRequest.new({name: 'name_example'}) # CreateSheetRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a sheet.
  result = api_instance.create_sheet(create_sheet_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->create_sheet: #{e}"
end
```

#### Using the create_sheet_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Sheet>, Integer, Hash)> create_sheet_with_http_info(create_sheet_request, opts)

```ruby
begin
  # Create a sheet.
  data, status_code, headers = api_instance.create_sheet_with_http_info(create_sheet_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Sheet>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->create_sheet_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_sheet_request** | [**CreateSheetRequest**](CreateSheetRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_sheet_row

> <Row> create_sheet_row(id, create_row_request, opts)

Insert a row.

Inserts a row at `index` (zero-based) or appends to the end when `index` is omitted. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
create_row_request = Spatio::CreateRowRequest.new({cells: { key: 3.56}}) # CreateRowRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Insert a row.
  result = api_instance.create_sheet_row(id, create_row_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->create_sheet_row: #{e}"
end
```

#### Using the create_sheet_row_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Row>, Integer, Hash)> create_sheet_row_with_http_info(id, create_row_request, opts)

```ruby
begin
  # Insert a row.
  data, status_code, headers = api_instance.create_sheet_row_with_http_info(id, create_row_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Row>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->create_sheet_row_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **create_row_request** | [**CreateRowRequest**](CreateRowRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Row**](Row.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_sheet

> <SuccessFlag> delete_sheet(id, opts)

Delete a sheet.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a sheet.
  result = api_instance.delete_sheet(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->delete_sheet: #{e}"
end
```

#### Using the delete_sheet_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_sheet_with_http_info(id, opts)

```ruby
begin
  # Delete a sheet.
  data, status_code, headers = api_instance.delete_sheet_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->delete_sheet_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_sheet_row

> <SuccessFlag> delete_sheet_row(id, row_index, opts)

Delete a row.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
row_index = 56 # Integer | Zero-based row index.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a row.
  result = api_instance.delete_sheet_row(id, row_index, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->delete_sheet_row: #{e}"
end
```

#### Using the delete_sheet_row_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_sheet_row_with_http_info(id, row_index, opts)

```ruby
begin
  # Delete a row.
  data, status_code, headers = api_instance.delete_sheet_row_with_http_info(id, row_index, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->delete_sheet_row_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **row_index** | **Integer** | Zero-based row index. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_sheet

> <Sheet> get_sheet(id, opts)

Fetch one sheet.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one sheet.
  result = api_instance.get_sheet(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->get_sheet: #{e}"
end
```

#### Using the get_sheet_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Sheet>, Integer, Hash)> get_sheet_with_http_info(id, opts)

```ruby
begin
  # Fetch one sheet.
  data, status_code, headers = api_instance.get_sheet_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Sheet>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->get_sheet_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_sheet_rows

> <RowList> list_sheet_rows(id, opts)

List rows in a sheet.

Single-account row list. Unlike `GET /v1/sheets`, row listing always targets the one account that owns the sheet, so the response is a plain `{ rows, total }` rather than a fan-out envelope. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List rows in a sheet.
  result = api_instance.list_sheet_rows(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->list_sheet_rows: #{e}"
end
```

#### Using the list_sheet_rows_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RowList>, Integer, Hash)> list_sheet_rows_with_http_info(id, opts)

```ruby
begin
  # List rows in a sheet.
  data, status_code, headers = api_instance.list_sheet_rows_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RowList>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->list_sheet_rows_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional][default to 100] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**RowList**](RowList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_sheets

> <SheetListEnvelope> list_sheets(opts)

List sheets across connected accounts.

Fan-out list. Returns every sheet visible to the caller across every connected sheets provider, paginated by `limit` / `offset`. Pass `?accountId=` or `?provider=` to scope to a single source. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List sheets across connected accounts.
  result = api_instance.list_sheets(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->list_sheets: #{e}"
end
```

#### Using the list_sheets_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SheetListEnvelope>, Integer, Hash)> list_sheets_with_http_info(opts)

```ruby
begin
  # List sheets across connected accounts.
  data, status_code, headers = api_instance.list_sheets_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SheetListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->list_sheets_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **limit** | **Integer** |  | [optional][default to 50] |
| **offset** | **Integer** |  | [optional][default to 0] |

### Return type

[**SheetListEnvelope**](SheetListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_sheet

> <Sheet> update_sheet(id, update_sheet_request, opts)

Update a sheet (partial).

Partial update of sheet metadata. The renderer also calls this via `PUT /v1/sheets/{id}` for autosave parity; both verbs invoke the same handler. Per-cell and per-row mutations live on their dedicated endpoints, not here. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
update_sheet_request = Spatio::UpdateSheetRequest.new # UpdateSheetRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a sheet (partial).
  result = api_instance.update_sheet(id, update_sheet_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet: #{e}"
end
```

#### Using the update_sheet_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Sheet>, Integer, Hash)> update_sheet_with_http_info(id, update_sheet_request, opts)

```ruby
begin
  # Update a sheet (partial).
  data, status_code, headers = api_instance.update_sheet_with_http_info(id, update_sheet_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Sheet>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **update_sheet_request** | [**UpdateSheetRequest**](UpdateSheetRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Sheet**](Sheet.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sheet_cell

> <Cell> update_sheet_cell(id, row_index, column, update_cell_request, opts)

Update a single cell.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
row_index = 56 # Integer | Zero-based row index.
column = 'column_example' # String | Column identifier. Provider-specific — usually a letter (`A`, `AB`) for spreadsheet providers or a column key string for structured providers. 
update_cell_request = Spatio::UpdateCellRequest.new({value: 3.56}) # UpdateCellRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a single cell.
  result = api_instance.update_sheet_cell(id, row_index, column, update_cell_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet_cell: #{e}"
end
```

#### Using the update_sheet_cell_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Cell>, Integer, Hash)> update_sheet_cell_with_http_info(id, row_index, column, update_cell_request, opts)

```ruby
begin
  # Update a single cell.
  data, status_code, headers = api_instance.update_sheet_cell_with_http_info(id, row_index, column, update_cell_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Cell>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet_cell_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **row_index** | **Integer** | Zero-based row index. |  |
| **column** | **String** | Column identifier. Provider-specific — usually a letter (&#x60;A&#x60;, &#x60;AB&#x60;) for spreadsheet providers or a column key string for structured providers.  |  |
| **update_cell_request** | [**UpdateCellRequest**](UpdateCellRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Cell**](Cell.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sheet_row

> <Row> update_sheet_row(id, row_index, update_row_request, opts)

Update a row (sparse).

Sparse update — keys present in `cells` overwrite that column; keys absent are preserved. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SheetsApi.new
id = 'id_example' # String | Sheet id.
row_index = 56 # Integer | Zero-based row index.
update_row_request = Spatio::UpdateRowRequest.new({cells: { key: 3.56}}) # UpdateRowRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a row (sparse).
  result = api_instance.update_sheet_row(id, row_index, update_row_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet_row: #{e}"
end
```

#### Using the update_sheet_row_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Row>, Integer, Hash)> update_sheet_row_with_http_info(id, row_index, update_row_request, opts)

```ruby
begin
  # Update a row (sparse).
  data, status_code, headers = api_instance.update_sheet_row_with_http_info(id, row_index, update_row_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Row>
rescue Spatio::ApiError => e
  puts "Error when calling SheetsApi->update_sheet_row_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Sheet id. |  |
| **row_index** | **Integer** | Zero-based row index. |  |
| **update_row_request** | [**UpdateRowRequest**](UpdateRowRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Row**](Row.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

