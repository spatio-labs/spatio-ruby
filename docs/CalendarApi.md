# Spatio::CalendarApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_calendar_event**](CalendarApi.md#create_calendar_event) | **POST** /v1/calendar/events | Create a calendar event. |
| [**delete_calendar_event**](CalendarApi.md#delete_calendar_event) | **DELETE** /v1/calendar/events/{id} | Delete an event. |
| [**get_calendar_capabilities**](CalendarApi.md#get_calendar_capabilities) | **GET** /v1/calendar/capabilities | Per-account capability flags. |
| [**get_calendar_event**](CalendarApi.md#get_calendar_event) | **GET** /v1/calendar/events/{id} | Fetch one event. |
| [**list_calendar_events**](CalendarApi.md#list_calendar_events) | **GET** /v1/calendar/events | List calendar events across connected accounts. |
| [**list_calendar_providers**](CalendarApi.md#list_calendar_providers) | **GET** /v1/calendar/providers | List supported calendar providers. |
| [**sync_calendar**](CalendarApi.md#sync_calendar) | **POST** /v1/calendar/sync | Trigger a sync across connected calendar accounts. |
| [**update_calendar_event**](CalendarApi.md#update_calendar_event) | **PATCH** /v1/calendar/events/{id} | Update an event (sparse). |
| [**workspace_create_calendar_event**](CalendarApi.md#workspace_create_calendar_event) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calendar/events | Workspace-scoped create-event (RBAC-protected). |
| [**workspace_delete_calendar_event**](CalendarApi.md#workspace_delete_calendar_event) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |
| [**workspace_get_calendar_event**](CalendarApi.md#workspace_get_calendar_event) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |
| [**workspace_list_calendar_events**](CalendarApi.md#workspace_list_calendar_events) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/events | Workspace-scoped list-events (RBAC-protected). |
| [**workspace_list_calendar_providers**](CalendarApi.md#workspace_list_calendar_providers) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calendar/providers | Workspace-scoped calendar providers. |
| [**workspace_update_calendar_event**](CalendarApi.md#workspace_update_calendar_event) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/calendar/events/{id} |  |


## create_calendar_event

> <CreateCalendarEvent201Response> create_calendar_event(create_event_request, opts)

Create a calendar event.

Single-account create. `account_id` is required (no auto-resolve for write operations). Reminder array is mirrored into native tasks under the hood; conference data is auto-attached when `conference_type` is supplied. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
create_event_request = Spatio::CreateEventRequest.new({account_id: 'account_id_example', event: Spatio::SpatioEvent.new({id: 'id_example', title: 'title_example', start_time: Time.now, end_time: Time.now, all_day: false, status: 'status_example', visibility: 'visibility_example', busy: false, account_id: 'account_id_example', provider_id: 'provider_id_example', created_at: Time.now, updated_at: Time.now})}) # CreateEventRequest | 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a calendar event.
  result = api_instance.create_calendar_event(create_event_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->create_calendar_event: #{e}"
end
```

#### Using the create_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCalendarEvent201Response>, Integer, Hash)> create_calendar_event_with_http_info(create_event_request, opts)

```ruby
begin
  # Create a calendar event.
  data, status_code, headers = api_instance.create_calendar_event_with_http_info(create_event_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCalendarEvent201Response>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->create_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_event_request** | [**CreateEventRequest**](CreateEventRequest.md) |  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CreateCalendarEvent201Response**](CreateCalendarEvent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_calendar_event

> <CalendarOperationResult> delete_calendar_event(id, account_id, opts)

Delete an event.

Hard delete (no soft-delete / trash). Cascades to any reminder tasks the platform created from this event. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
id = 'id_example' # String | Event id.
account_id = 'account_id_example' # String | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete an event.
  result = api_instance.delete_calendar_event(id, account_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->delete_calendar_event: #{e}"
end
```

#### Using the delete_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarOperationResult>, Integer, Hash)> delete_calendar_event_with_http_info(id, account_id, opts)

```ruby
begin
  # Delete an event.
  data, status_code, headers = api_instance.delete_calendar_event_with_http_info(id, account_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarOperationResult>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->delete_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Event id. |  |
| **account_id** | **String** | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**CalendarOperationResult**](CalendarOperationResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_calendar_capabilities

> <CalendarCapabilitiesResponse> get_calendar_capabilities(account_id)

Per-account capability flags.

Returns the capabilities the provider declares for the given connected account. The renderer uses these to enable/disable form fields (recurrence picker, attendee inputs, etc.). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
account_id = 'account_id_example' # String | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 

begin
  # Per-account capability flags.
  result = api_instance.get_calendar_capabilities(account_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->get_calendar_capabilities: #{e}"
end
```

#### Using the get_calendar_capabilities_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarCapabilitiesResponse>, Integer, Hash)> get_calendar_capabilities_with_http_info(account_id)

```ruby
begin
  # Per-account capability flags.
  data, status_code, headers = api_instance.get_calendar_capabilities_with_http_info(account_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarCapabilitiesResponse>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->get_calendar_capabilities_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  |  |

### Return type

[**CalendarCapabilitiesResponse**](CalendarCapabilitiesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_calendar_event

> <SpatioEvent> get_calendar_event(id, account_id, opts)

Fetch one event.

Requires `?account_id=` to identify the source account. Response is the bare `Event` (not wrapped in CalendarOperationResult — distinct from the list/create/update shapes). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
id = 'id_example' # String | Event id.
account_id = 'account_id_example' # String | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses `accountId`). Required for single-event operations. 
opts = {
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one event.
  result = api_instance.get_calendar_event(id, account_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->get_calendar_event: #{e}"
end
```

#### Using the get_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioEvent>, Integer, Hash)> get_calendar_event_with_http_info(id, account_id, opts)

```ruby
begin
  # Fetch one event.
  data, status_code, headers = api_instance.get_calendar_event_with_http_info(id, account_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioEvent>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->get_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Event id. |  |
| **account_id** | **String** | Connected-account id (snake_case in this platform — the rest of the SpatioAPI uses &#x60;accountId&#x60;). Required for single-event operations.  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SpatioEvent**](SpatioEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_calendar_events

> <ListCalendarEvents200Response> list_calendar_events(opts)

List calendar events across connected accounts.

Fan-out list. Returns events across every connected calendar provider unless filtered by `account_ids[]` or `providers[]`. Supports the cross-platform repeated-or-comma-separated filter syntax (`?account_ids=a&account_ids=b` or `?account_ids=a,b`).  Time bounds (`timeMin` / `timeMax`) accept both RFC3339 and RFC3339Nano. The handler also accepts the snake_case `time_min` / `time_max` for direct curl callers; the spec models the camelCase form because that's what the renderer and SDKs use. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
opts = {
  account_ids: ['inner_example'], # Array<String> | Repeatable. Restrict to specific connected accounts.
  providers: ['inner_example'], # Array<String> | Repeatable. Restrict to provider ids (`google-calendar`, etc.).
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  time_min: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Inclusive lower-bound time. RFC3339 or RFC3339Nano.
  time_max: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Inclusive upper-bound time.
  limit: 56 # Integer | Max events to return per page (default 50).
}

begin
  # List calendar events across connected accounts.
  result = api_instance.list_calendar_events(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->list_calendar_events: #{e}"
end
```

#### Using the list_calendar_events_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCalendarEvents200Response>, Integer, Hash)> list_calendar_events_with_http_info(opts)

```ruby
begin
  # List calendar events across connected accounts.
  data, status_code, headers = api_instance.list_calendar_events_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCalendarEvents200Response>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->list_calendar_events_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_ids** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to specific connected accounts. | [optional] |
| **providers** | [**Array&lt;String&gt;**](String.md) | Repeatable. Restrict to provider ids (&#x60;google-calendar&#x60;, etc.). | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **time_min** | **Time** | Inclusive lower-bound time. RFC3339 or RFC3339Nano. | [optional] |
| **time_max** | **Time** | Inclusive upper-bound time. | [optional] |
| **limit** | **Integer** | Max events to return per page (default 50). | [optional][default to 50] |

### Return type

[**ListCalendarEvents200Response**](ListCalendarEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_calendar_providers

> <CalendarProvidersInfo> list_calendar_providers

List supported calendar providers.

Static list of provider ids the Calendar platform can connect to. Returned regardless of which providers the caller has actually authorized. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new

begin
  # List supported calendar providers.
  result = api_instance.list_calendar_providers
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->list_calendar_providers: #{e}"
end
```

#### Using the list_calendar_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarProvidersInfo>, Integer, Hash)> list_calendar_providers_with_http_info

```ruby
begin
  # List supported calendar providers.
  data, status_code, headers = api_instance.list_calendar_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarProvidersInfo>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->list_calendar_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CalendarProvidersInfo**](CalendarProvidersInfo.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## sync_calendar

> <CalendarSyncResponse> sync_calendar(opts)

Trigger a sync across connected calendar accounts.

Enqueues sync jobs (one per connected calendar account) and returns immediately with the job ids. Pass `?wait=true` to block until all jobs complete (10-second polling budget); the response is then `200` with `waited: true` and a `timed_out` flag if any job didn't finish in time. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
opts = {
  wait: true # Boolean | Block until all sync jobs finish (10s timeout).
}

begin
  # Trigger a sync across connected calendar accounts.
  result = api_instance.sync_calendar(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->sync_calendar: #{e}"
end
```

#### Using the sync_calendar_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalendarSyncResponse>, Integer, Hash)> sync_calendar_with_http_info(opts)

```ruby
begin
  # Trigger a sync across connected calendar accounts.
  data, status_code, headers = api_instance.sync_calendar_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalendarSyncResponse>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->sync_calendar_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **wait** | **Boolean** | Block until all sync jobs finish (10s timeout). | [optional][default to false] |

### Return type

[**CalendarSyncResponse**](CalendarSyncResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_calendar_event

> <CreateCalendarEvent201Response> update_calendar_event(id, update_event_request, opts)

Update an event (sparse).

Partial update. `account_id` may be supplied in the body (preferred) or as `?account_id=` query param — the renderer's update path puts it in the URL while create puts it in the body. `updates` is a free-form map; the platform's capability gate rejects fields the provider doesn't support. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
id = 'id_example' # String | Event id.
update_event_request = Spatio::UpdateEventRequest.new({account_id: 'account_id_example', updates: { key: 3.56}}) # UpdateEventRequest | 
opts = {
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  account_id: 'account_id_example' # String | Optional account-id filter (snake_case).
}

begin
  # Update an event (sparse).
  result = api_instance.update_calendar_event(id, update_event_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->update_calendar_event: #{e}"
end
```

#### Using the update_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCalendarEvent201Response>, Integer, Hash)> update_calendar_event_with_http_info(id, update_event_request, opts)

```ruby
begin
  # Update an event (sparse).
  data, status_code, headers = api_instance.update_calendar_event_with_http_info(id, update_event_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCalendarEvent201Response>
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->update_calendar_event_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Event id. |  |
| **update_event_request** | [**UpdateEventRequest**](UpdateEventRequest.md) |  |  |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **account_id** | **String** | Optional account-id filter (snake_case). | [optional] |

### Return type

[**CreateCalendarEvent201Response**](CreateCalendarEvent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_calendar_event

> Hash&lt;String, Object&gt; workspace_create_calendar_event(org, workspace, request_body)

Workspace-scoped create-event (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Workspace-scoped create-event (RBAC-protected).
  result = api_instance.workspace_create_calendar_event(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_create_calendar_event: #{e}"
end
```

#### Using the workspace_create_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_calendar_event_with_http_info(org, workspace, request_body)

```ruby
begin
  # Workspace-scoped create-event (RBAC-protected).
  data, status_code, headers = api_instance.workspace_create_calendar_event_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_create_calendar_event_with_http_info: #{e}"
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


## workspace_delete_calendar_event

> workspace_delete_calendar_event(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_delete_calendar_event(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_delete_calendar_event: #{e}"
end
```

#### Using the workspace_delete_calendar_event_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_calendar_event_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_calendar_event_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_delete_calendar_event_with_http_info: #{e}"
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


## workspace_get_calendar_event

> Hash&lt;String, Object&gt; workspace_get_calendar_event(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_calendar_event(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_get_calendar_event: #{e}"
end
```

#### Using the workspace_get_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_calendar_event_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_calendar_event_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_get_calendar_event_with_http_info: #{e}"
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


## workspace_list_calendar_events

> Hash&lt;String, Object&gt; workspace_list_calendar_events(org, workspace)

Workspace-scoped list-events (RBAC-protected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  # Workspace-scoped list-events (RBAC-protected).
  result = api_instance.workspace_list_calendar_events(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_list_calendar_events: #{e}"
end
```

#### Using the workspace_list_calendar_events_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_calendar_events_with_http_info(org, workspace)

```ruby
begin
  # Workspace-scoped list-events (RBAC-protected).
  data, status_code, headers = api_instance.workspace_list_calendar_events_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_list_calendar_events_with_http_info: #{e}"
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


## workspace_list_calendar_providers

> Hash&lt;String, Object&gt; workspace_list_calendar_providers(org, workspace)

Workspace-scoped calendar providers.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  # Workspace-scoped calendar providers.
  result = api_instance.workspace_list_calendar_providers(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_list_calendar_providers: #{e}"
end
```

#### Using the workspace_list_calendar_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_calendar_providers_with_http_info(org, workspace)

```ruby
begin
  # Workspace-scoped calendar providers.
  data, status_code, headers = api_instance.workspace_list_calendar_providers_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_list_calendar_providers_with_http_info: #{e}"
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


## workspace_update_calendar_event

> Hash&lt;String, Object&gt; workspace_update_calendar_event(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CalendarApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_calendar_event(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_update_calendar_event: #{e}"
end
```

#### Using the workspace_update_calendar_event_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_calendar_event_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_calendar_event_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CalendarApi->workspace_update_calendar_event_with_http_info: #{e}"
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

