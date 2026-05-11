# Spatio::RoutinesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**claim_routine_run**](RoutinesApi.md#claim_routine_run) | **POST** /v1/routines/runs/{id}/claim | Worker claims a queued run. |
| [**complete_routine_run**](RoutinesApi.md#complete_routine_run) | **POST** /v1/routines/runs/{id}/complete | Worker marks a run complete. |
| [**create_routine**](RoutinesApi.md#create_routine) | **POST** /v1/routines | Create a routine. |
| [**delete_routine**](RoutinesApi.md#delete_routine) | **DELETE** /v1/routines/{id} | Delete a routine. |
| [**get_routine**](RoutinesApi.md#get_routine) | **GET** /v1/routines/{id} | Fetch a routine. |
| [**list_routine_runs**](RoutinesApi.md#list_routine_runs) | **GET** /v1/routines/{id}/runs | List runs for a routine. |
| [**list_routines**](RoutinesApi.md#list_routines) | **GET** /v1/routines | List routines for the caller&#39;s workspace. |
| [**run_routine_now**](RoutinesApi.md#run_routine_now) | **POST** /v1/routines/{id}/run-now | Trigger an ad-hoc run. |
| [**update_routine**](RoutinesApi.md#update_routine) | **PATCH** /v1/routines/{id} | Update a routine. |
| [**update_routine_run_progress**](RoutinesApi.md#update_routine_run_progress) | **POST** /v1/routines/runs/{id}/progress | Worker reports progress. |


## claim_routine_run

> <RoutineRun> claim_routine_run(id)

Worker claims a queued run.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 

begin
  # Worker claims a queued run.
  result = api_instance.claim_routine_run(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->claim_routine_run: #{e}"
end
```

#### Using the claim_routine_run_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineRun>, Integer, Hash)> claim_routine_run_with_http_info(id)

```ruby
begin
  # Worker claims a queued run.
  data, status_code, headers = api_instance.claim_routine_run_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineRun>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->claim_routine_run_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## complete_routine_run

> <RoutineRun> complete_routine_run(id, routine_run_complete_request)

Worker marks a run complete.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 
routine_run_complete_request = Spatio::RoutineRunCompleteRequest.new # RoutineRunCompleteRequest | 

begin
  # Worker marks a run complete.
  result = api_instance.complete_routine_run(id, routine_run_complete_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->complete_routine_run: #{e}"
end
```

#### Using the complete_routine_run_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineRun>, Integer, Hash)> complete_routine_run_with_http_info(id, routine_run_complete_request)

```ruby
begin
  # Worker marks a run complete.
  data, status_code, headers = api_instance.complete_routine_run_with_http_info(id, routine_run_complete_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineRun>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->complete_routine_run_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **routine_run_complete_request** | [**RoutineRunCompleteRequest**](RoutineRunCompleteRequest.md) |  |  |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_routine

> <Routine> create_routine(create_routine_request)

Create a routine.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
create_routine_request = Spatio::CreateRoutineRequest.new({name: 'name_example'}) # CreateRoutineRequest | 

begin
  # Create a routine.
  result = api_instance.create_routine(create_routine_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->create_routine: #{e}"
end
```

#### Using the create_routine_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Routine>, Integer, Hash)> create_routine_with_http_info(create_routine_request)

```ruby
begin
  # Create a routine.
  data, status_code, headers = api_instance.create_routine_with_http_info(create_routine_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Routine>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->create_routine_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_routine_request** | [**CreateRoutineRequest**](CreateRoutineRequest.md) |  |  |

### Return type

[**Routine**](Routine.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_routine

> delete_routine(id)

Delete a routine.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 

begin
  # Delete a routine.
  api_instance.delete_routine(id)
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->delete_routine: #{e}"
end
```

#### Using the delete_routine_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_routine_with_http_info(id)

```ruby
begin
  # Delete a routine.
  data, status_code, headers = api_instance.delete_routine_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->delete_routine_with_http_info: #{e}"
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


## get_routine

> <Routine> get_routine(id)

Fetch a routine.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 

begin
  # Fetch a routine.
  result = api_instance.get_routine(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->get_routine: #{e}"
end
```

#### Using the get_routine_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Routine>, Integer, Hash)> get_routine_with_http_info(id)

```ruby
begin
  # Fetch a routine.
  data, status_code, headers = api_instance.get_routine_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Routine>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->get_routine_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Routine**](Routine.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_routine_runs

> <RoutineRunListResponse> list_routine_runs(id)

List runs for a routine.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 

begin
  # List runs for a routine.
  result = api_instance.list_routine_runs(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->list_routine_runs: #{e}"
end
```

#### Using the list_routine_runs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineRunListResponse>, Integer, Hash)> list_routine_runs_with_http_info(id)

```ruby
begin
  # List runs for a routine.
  data, status_code, headers = api_instance.list_routine_runs_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineRunListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->list_routine_runs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**RoutineRunListResponse**](RoutineRunListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_routines

> <RoutineListResponse> list_routines(opts)

List routines for the caller's workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
opts = {
  workspace_id: 'workspace_id_example', # String | 
  status: 'status_example' # String | 
}

begin
  # List routines for the caller's workspace.
  result = api_instance.list_routines(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->list_routines: #{e}"
end
```

#### Using the list_routines_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineListResponse>, Integer, Hash)> list_routines_with_http_info(opts)

```ruby
begin
  # List routines for the caller's workspace.
  data, status_code, headers = api_instance.list_routines_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->list_routines_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |

### Return type

[**RoutineListResponse**](RoutineListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## run_routine_now

> <RoutineRun> run_routine_now(id)

Trigger an ad-hoc run.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 

begin
  # Trigger an ad-hoc run.
  result = api_instance.run_routine_now(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->run_routine_now: #{e}"
end
```

#### Using the run_routine_now_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineRun>, Integer, Hash)> run_routine_now_with_http_info(id)

```ruby
begin
  # Trigger an ad-hoc run.
  data, status_code, headers = api_instance.run_routine_now_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineRun>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->run_routine_now_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_routine

> <Routine> update_routine(id, update_routine_request)

Update a routine.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 
update_routine_request = Spatio::UpdateRoutineRequest.new # UpdateRoutineRequest | 

begin
  # Update a routine.
  result = api_instance.update_routine(id, update_routine_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->update_routine: #{e}"
end
```

#### Using the update_routine_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Routine>, Integer, Hash)> update_routine_with_http_info(id, update_routine_request)

```ruby
begin
  # Update a routine.
  data, status_code, headers = api_instance.update_routine_with_http_info(id, update_routine_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Routine>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->update_routine_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_routine_request** | [**UpdateRoutineRequest**](UpdateRoutineRequest.md) |  |  |

### Return type

[**Routine**](Routine.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_routine_run_progress

> <RoutineRun> update_routine_run_progress(id, routine_run_progress_request)

Worker reports progress.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RoutinesApi.new
id = 'id_example' # String | 
routine_run_progress_request = Spatio::RoutineRunProgressRequest.new # RoutineRunProgressRequest | 

begin
  # Worker reports progress.
  result = api_instance.update_routine_run_progress(id, routine_run_progress_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->update_routine_run_progress: #{e}"
end
```

#### Using the update_routine_run_progress_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RoutineRun>, Integer, Hash)> update_routine_run_progress_with_http_info(id, routine_run_progress_request)

```ruby
begin
  # Worker reports progress.
  data, status_code, headers = api_instance.update_routine_run_progress_with_http_info(id, routine_run_progress_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RoutineRun>
rescue Spatio::ApiError => e
  puts "Error when calling RoutinesApi->update_routine_run_progress_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **routine_run_progress_request** | [**RoutineRunProgressRequest**](RoutineRunProgressRequest.md) |  |  |

### Return type

[**RoutineRun**](RoutineRun.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

