# Spatio::RealtimeApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**issue_collaboration_token**](RealtimeApi.md#issue_collaboration_token) | **POST** /v1/realtime/collaboration-token | Exchange a bearer token for a short-lived Yjs collaboration JWT. |


## issue_collaboration_token

> <IssueCollaborationToken200Response> issue_collaboration_token(opts)

Exchange a bearer token for a short-lived Yjs collaboration JWT.

The Yjs Cloudflare Worker that powers live document collaboration (`wss://realtime-collaboration.<account>.workers.dev`) only accepts platform-signed JWTs. Third-party clients holding an OAuth access token or PAT call this endpoint to mint a 5-minute collaboration JWT they can present to the worker.  The minted JWT inherits user + workspace identity from the presenting bearer token. Optionally scope it to a single room by supplying `room` in the request body. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RealtimeApi.new
opts = {
  issue_collaboration_token_request: Spatio::IssueCollaborationTokenRequest.new # IssueCollaborationTokenRequest | 
}

begin
  # Exchange a bearer token for a short-lived Yjs collaboration JWT.
  result = api_instance.issue_collaboration_token(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RealtimeApi->issue_collaboration_token: #{e}"
end
```

#### Using the issue_collaboration_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IssueCollaborationToken200Response>, Integer, Hash)> issue_collaboration_token_with_http_info(opts)

```ruby
begin
  # Exchange a bearer token for a short-lived Yjs collaboration JWT.
  data, status_code, headers = api_instance.issue_collaboration_token_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IssueCollaborationToken200Response>
rescue Spatio::ApiError => e
  puts "Error when calling RealtimeApi->issue_collaboration_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **issue_collaboration_token_request** | [**IssueCollaborationTokenRequest**](IssueCollaborationTokenRequest.md) |  | [optional] |

### Return type

[**IssueCollaborationToken200Response**](IssueCollaborationToken200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

