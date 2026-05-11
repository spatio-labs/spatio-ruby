# Spatio::CallsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_call**](CallsApi.md#create_call) | **POST** /v1/calls | Start a new call. |
| [**create_meeting_room**](CallsApi.md#create_meeting_room) | **POST** /v1/calls/rooms | Create a persistent meeting room. |
| [**delete_call_recording**](CallsApi.md#delete_call_recording) | **DELETE** /v1/calls/recordings/{recordingId} | Delete a recording. |
| [**end_call**](CallsApi.md#end_call) | **POST** /v1/calls/{id}/end | End a call (host only). |
| [**get_bandwidth_history**](CallsApi.md#get_bandwidth_history) | **GET** /v1/calls/bandwidth/history | Time-series bandwidth metrics. |
| [**get_bandwidth_summary**](CallsApi.md#get_bandwidth_summary) | **GET** /v1/calls/bandwidth/summary | Aggregate bandwidth metrics. |
| [**get_call**](CallsApi.md#get_call) | **GET** /v1/calls/{id} | Fetch a call. |
| [**get_meeting_room**](CallsApi.md#get_meeting_room) | **GET** /v1/calls/rooms/{id} | Fetch a meeting room. |
| [**join_call**](CallsApi.md#join_call) | **POST** /v1/calls/{id}/join | Join a call. |
| [**leave_call**](CallsApi.md#leave_call) | **POST** /v1/calls/{id}/leave | Leave a call. |
| [**list_active_calls**](CallsApi.md#list_active_calls) | **GET** /v1/calls | List active calls. |
| [**list_call_recordings**](CallsApi.md#list_call_recordings) | **GET** /v1/calls/{id}/recordings | List recordings for a call. |
| [**start_call_recording**](CallsApi.md#start_call_recording) | **POST** /v1/calls/{id}/recordings/start | Start a recording (host only). |
| [**stop_call_recording**](CallsApi.md#stop_call_recording) | **POST** /v1/calls/{id}/recordings/{recordingId}/stop | Stop an in-progress recording. |
| [**update_call_participant_state**](CallsApi.md#update_call_participant_state) | **PATCH** /v1/calls/{id}/participant | Toggle participant audio/video/screen-share state. |
| [**workspace_create_call**](CallsApi.md#workspace_create_call) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**workspace_create_meeting_room**](CallsApi.md#workspace_create_meeting_room) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms |  |
| [**workspace_delete_call_recording**](CallsApi.md#workspace_delete_call_recording) | **DELETE** /v1/organizations/{org}/workspaces/{workspace}/calls/recordings/{recordingId} |  |
| [**workspace_end_call**](CallsApi.md#workspace_end_call) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/end |  |
| [**workspace_get_bandwidth_history**](CallsApi.md#workspace_get_bandwidth_history) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/history |  |
| [**workspace_get_bandwidth_summary**](CallsApi.md#workspace_get_bandwidth_summary) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/bandwidth/summary |  |
| [**workspace_get_call**](CallsApi.md#workspace_get_call) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id} |  |
| [**workspace_get_meeting_room**](CallsApi.md#workspace_get_meeting_room) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/rooms/{id} |  |
| [**workspace_join_call**](CallsApi.md#workspace_join_call) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/join |  |
| [**workspace_leave_call**](CallsApi.md#workspace_leave_call) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/leave |  |
| [**workspace_list_active_calls**](CallsApi.md#workspace_list_active_calls) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls |  |
| [**workspace_list_call_recordings**](CallsApi.md#workspace_list_call_recordings) | **GET** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings |  |
| [**workspace_start_call_recording**](CallsApi.md#workspace_start_call_recording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/start |  |
| [**workspace_stop_call_recording**](CallsApi.md#workspace_stop_call_recording) | **POST** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/recordings/{recordingId}/stop |  |
| [**workspace_update_call_participant**](CallsApi.md#workspace_update_call_participant) | **PATCH** /v1/organizations/{org}/workspaces/{workspace}/calls/{id}/participant |  |


## create_call

> <SpatioCall> create_call(opts)

Start a new call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
opts = {
  create_call_request: Spatio::CreateCallRequest.new # CreateCallRequest | 
}

begin
  # Start a new call.
  result = api_instance.create_call(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->create_call: #{e}"
end
```

#### Using the create_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioCall>, Integer, Hash)> create_call_with_http_info(opts)

```ruby
begin
  # Start a new call.
  data, status_code, headers = api_instance.create_call_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioCall>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->create_call_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_call_request** | [**CreateCallRequest**](CreateCallRequest.md) |  | [optional] |

### Return type

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_meeting_room

> <MeetingRoom> create_meeting_room(create_meeting_room_request)

Create a persistent meeting room.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
create_meeting_room_request = Spatio::CreateMeetingRoomRequest.new({name: 'name_example'}) # CreateMeetingRoomRequest | 

begin
  # Create a persistent meeting room.
  result = api_instance.create_meeting_room(create_meeting_room_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->create_meeting_room: #{e}"
end
```

#### Using the create_meeting_room_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MeetingRoom>, Integer, Hash)> create_meeting_room_with_http_info(create_meeting_room_request)

```ruby
begin
  # Create a persistent meeting room.
  data, status_code, headers = api_instance.create_meeting_room_with_http_info(create_meeting_room_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MeetingRoom>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->create_meeting_room_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_meeting_room_request** | [**CreateMeetingRoomRequest**](CreateMeetingRoomRequest.md) |  |  |

### Return type

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_call_recording

> delete_call_recording(recording_id)

Delete a recording.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
recording_id = 'recording_id_example' # String | 

begin
  # Delete a recording.
  api_instance.delete_call_recording(recording_id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->delete_call_recording: #{e}"
end
```

#### Using the delete_call_recording_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_call_recording_with_http_info(recording_id)

```ruby
begin
  # Delete a recording.
  data, status_code, headers = api_instance.delete_call_recording_with_http_info(recording_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->delete_call_recording_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recording_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## end_call

> end_call(id)

End a call (host only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # End a call (host only).
  api_instance.end_call(id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->end_call: #{e}"
end
```

#### Using the end_call_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> end_call_with_http_info(id)

```ruby
begin
  # End a call (host only).
  data, status_code, headers = api_instance.end_call_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->end_call_with_http_info: #{e}"
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


## get_bandwidth_history

> Hash&lt;String, Object&gt; get_bandwidth_history

Time-series bandwidth metrics.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new

begin
  # Time-series bandwidth metrics.
  result = api_instance.get_bandwidth_history
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_bandwidth_history: #{e}"
end
```

#### Using the get_bandwidth_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_bandwidth_history_with_http_info

```ruby
begin
  # Time-series bandwidth metrics.
  data, status_code, headers = api_instance.get_bandwidth_history_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_bandwidth_history_with_http_info: #{e}"
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


## get_bandwidth_summary

> Hash&lt;String, Object&gt; get_bandwidth_summary

Aggregate bandwidth metrics.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new

begin
  # Aggregate bandwidth metrics.
  result = api_instance.get_bandwidth_summary
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_bandwidth_summary: #{e}"
end
```

#### Using the get_bandwidth_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_bandwidth_summary_with_http_info

```ruby
begin
  # Aggregate bandwidth metrics.
  data, status_code, headers = api_instance.get_bandwidth_summary_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_bandwidth_summary_with_http_info: #{e}"
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


## get_call

> <SpatioCall> get_call(id)

Fetch a call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # Fetch a call.
  result = api_instance.get_call(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_call: #{e}"
end
```

#### Using the get_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SpatioCall>, Integer, Hash)> get_call_with_http_info(id)

```ruby
begin
  # Fetch a call.
  data, status_code, headers = api_instance.get_call_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SpatioCall>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_call_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**SpatioCall**](SpatioCall.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_meeting_room

> <MeetingRoom> get_meeting_room(id)

Fetch a meeting room.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # Fetch a meeting room.
  result = api_instance.get_meeting_room(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_meeting_room: #{e}"
end
```

#### Using the get_meeting_room_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MeetingRoom>, Integer, Hash)> get_meeting_room_with_http_info(id)

```ruby
begin
  # Fetch a meeting room.
  data, status_code, headers = api_instance.get_meeting_room_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MeetingRoom>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->get_meeting_room_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**MeetingRoom**](MeetingRoom.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## join_call

> Hash&lt;String, Object&gt; join_call(id)

Join a call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # Join a call.
  result = api_instance.join_call(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->join_call: #{e}"
end
```

#### Using the join_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> join_call_with_http_info(id)

```ruby
begin
  # Join a call.
  data, status_code, headers = api_instance.join_call_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->join_call_with_http_info: #{e}"
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


## leave_call

> leave_call(id)

Leave a call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # Leave a call.
  api_instance.leave_call(id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->leave_call: #{e}"
end
```

#### Using the leave_call_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> leave_call_with_http_info(id)

```ruby
begin
  # Leave a call.
  data, status_code, headers = api_instance.leave_call_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->leave_call_with_http_info: #{e}"
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


## list_active_calls

> <CallListResponse> list_active_calls

List active calls.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new

begin
  # List active calls.
  result = api_instance.list_active_calls
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->list_active_calls: #{e}"
end
```

#### Using the list_active_calls_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CallListResponse>, Integer, Hash)> list_active_calls_with_http_info

```ruby
begin
  # List active calls.
  data, status_code, headers = api_instance.list_active_calls_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CallListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->list_active_calls_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**CallListResponse**](CallListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_call_recordings

> <CallRecordingListResponse> list_call_recordings(id)

List recordings for a call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # List recordings for a call.
  result = api_instance.list_call_recordings(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->list_call_recordings: #{e}"
end
```

#### Using the list_call_recordings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CallRecordingListResponse>, Integer, Hash)> list_call_recordings_with_http_info(id)

```ruby
begin
  # List recordings for a call.
  data, status_code, headers = api_instance.list_call_recordings_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CallRecordingListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->list_call_recordings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**CallRecordingListResponse**](CallRecordingListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## start_call_recording

> <CallRecording> start_call_recording(id)

Start a recording (host only).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 

begin
  # Start a recording (host only).
  result = api_instance.start_call_recording(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->start_call_recording: #{e}"
end
```

#### Using the start_call_recording_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CallRecording>, Integer, Hash)> start_call_recording_with_http_info(id)

```ruby
begin
  # Start a recording (host only).
  data, status_code, headers = api_instance.start_call_recording_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CallRecording>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->start_call_recording_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## stop_call_recording

> <CallRecording> stop_call_recording(id, recording_id)

Stop an in-progress recording.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 
recording_id = 'recording_id_example' # String | 

begin
  # Stop an in-progress recording.
  result = api_instance.stop_call_recording(id, recording_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->stop_call_recording: #{e}"
end
```

#### Using the stop_call_recording_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CallRecording>, Integer, Hash)> stop_call_recording_with_http_info(id, recording_id)

```ruby
begin
  # Stop an in-progress recording.
  data, status_code, headers = api_instance.stop_call_recording_with_http_info(id, recording_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CallRecording>
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->stop_call_recording_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **recording_id** | **String** |  |  |

### Return type

[**CallRecording**](CallRecording.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_call_participant_state

> Hash&lt;String, Object&gt; update_call_participant_state(id, update_participant_state_request)

Toggle participant audio/video/screen-share state.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
id = 'id_example' # String | 
update_participant_state_request = Spatio::UpdateParticipantStateRequest.new # UpdateParticipantStateRequest | 

begin
  # Toggle participant audio/video/screen-share state.
  result = api_instance.update_call_participant_state(id, update_participant_state_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->update_call_participant_state: #{e}"
end
```

#### Using the update_call_participant_state_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> update_call_participant_state_with_http_info(id, update_participant_state_request)

```ruby
begin
  # Toggle participant audio/video/screen-share state.
  data, status_code, headers = api_instance.update_call_participant_state_with_http_info(id, update_participant_state_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->update_call_participant_state_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_participant_state_request** | [**UpdateParticipantStateRequest**](UpdateParticipantStateRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_call

> Hash&lt;String, Object&gt; workspace_create_call(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_call(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_create_call: #{e}"
end
```

#### Using the workspace_create_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_call_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_call_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_create_call_with_http_info: #{e}"
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


## workspace_create_meeting_room

> Hash&lt;String, Object&gt; workspace_create_meeting_room(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_meeting_room(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_create_meeting_room: #{e}"
end
```

#### Using the workspace_create_meeting_room_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_meeting_room_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_meeting_room_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_create_meeting_room_with_http_info: #{e}"
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


## workspace_delete_call_recording

> workspace_delete_call_recording(org, workspace, recording_id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
recording_id = 'recording_id_example' # String | 

begin
  
  api_instance.workspace_delete_call_recording(org, workspace, recording_id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_delete_call_recording: #{e}"
end
```

#### Using the workspace_delete_call_recording_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_delete_call_recording_with_http_info(org, workspace, recording_id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_delete_call_recording_with_http_info(org, workspace, recording_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_delete_call_recording_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **recording_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_end_call

> workspace_end_call(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_end_call(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_end_call: #{e}"
end
```

#### Using the workspace_end_call_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_end_call_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_end_call_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_end_call_with_http_info: #{e}"
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


## workspace_get_bandwidth_history

> Hash&lt;String, Object&gt; workspace_get_bandwidth_history(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_get_bandwidth_history(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_bandwidth_history: #{e}"
end
```

#### Using the workspace_get_bandwidth_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_bandwidth_history_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_bandwidth_history_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_bandwidth_history_with_http_info: #{e}"
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


## workspace_get_bandwidth_summary

> Hash&lt;String, Object&gt; workspace_get_bandwidth_summary(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_get_bandwidth_summary(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_bandwidth_summary: #{e}"
end
```

#### Using the workspace_get_bandwidth_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_bandwidth_summary_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_bandwidth_summary_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_bandwidth_summary_with_http_info: #{e}"
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


## workspace_get_call

> Hash&lt;String, Object&gt; workspace_get_call(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_call(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_call: #{e}"
end
```

#### Using the workspace_get_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_call_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_call_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_call_with_http_info: #{e}"
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


## workspace_get_meeting_room

> Hash&lt;String, Object&gt; workspace_get_meeting_room(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_get_meeting_room(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_meeting_room: #{e}"
end
```

#### Using the workspace_get_meeting_room_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_meeting_room_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_meeting_room_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_get_meeting_room_with_http_info: #{e}"
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


## workspace_join_call

> Hash&lt;String, Object&gt; workspace_join_call(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_join_call(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_join_call: #{e}"
end
```

#### Using the workspace_join_call_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_join_call_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_join_call_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_join_call_with_http_info: #{e}"
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


## workspace_leave_call

> workspace_leave_call(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  api_instance.workspace_leave_call(org, workspace, id)
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_leave_call: #{e}"
end
```

#### Using the workspace_leave_call_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> workspace_leave_call_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_leave_call_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_leave_call_with_http_info: #{e}"
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


## workspace_list_active_calls

> Hash&lt;String, Object&gt; workspace_list_active_calls(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_active_calls(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_list_active_calls: #{e}"
end
```

#### Using the workspace_list_active_calls_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_active_calls_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_active_calls_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_list_active_calls_with_http_info: #{e}"
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


## workspace_list_call_recordings

> Hash&lt;String, Object&gt; workspace_list_call_recordings(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_list_call_recordings(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_list_call_recordings: #{e}"
end
```

#### Using the workspace_list_call_recordings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_call_recordings_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_call_recordings_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_list_call_recordings_with_http_info: #{e}"
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


## workspace_start_call_recording

> Hash&lt;String, Object&gt; workspace_start_call_recording(org, workspace, id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 

begin
  
  result = api_instance.workspace_start_call_recording(org, workspace, id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_start_call_recording: #{e}"
end
```

#### Using the workspace_start_call_recording_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_start_call_recording_with_http_info(org, workspace, id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_start_call_recording_with_http_info(org, workspace, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_start_call_recording_with_http_info: #{e}"
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


## workspace_stop_call_recording

> Hash&lt;String, Object&gt; workspace_stop_call_recording(org, workspace, id, recording_id)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
recording_id = 'recording_id_example' # String | 

begin
  
  result = api_instance.workspace_stop_call_recording(org, workspace, id, recording_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_stop_call_recording: #{e}"
end
```

#### Using the workspace_stop_call_recording_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_stop_call_recording_with_http_info(org, workspace, id, recording_id)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_stop_call_recording_with_http_info(org, workspace, id, recording_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_stop_call_recording_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **id** | **String** |  |  |
| **recording_id** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_update_call_participant

> Hash&lt;String, Object&gt; workspace_update_call_participant(org, workspace, id, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::CallsApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
id = 'id_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_update_call_participant(org, workspace, id, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_update_call_participant: #{e}"
end
```

#### Using the workspace_update_call_participant_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_update_call_participant_with_http_info(org, workspace, id, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_update_call_participant_with_http_info(org, workspace, id, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling CallsApi->workspace_update_call_participant_with_http_info: #{e}"
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

