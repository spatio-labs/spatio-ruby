# Spatio::SearchApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**federated_search**](SearchApi.md#federated_search) | **POST** /v1/search | Cross-platform federated search. |


## federated_search

> <FederatedSearch200Response> federated_search(federated_search_request)

Cross-platform federated search.

Fans out to every platform's per-platform search method in parallel, merges + dedupes results, and returns them in a relevance-then-recency ranking with per-platform cursors for pagination. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SearchApi.new
federated_search_request = Spatio::FederatedSearchRequest.new({query: 'query_example'}) # FederatedSearchRequest | 

begin
  # Cross-platform federated search.
  result = api_instance.federated_search(federated_search_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SearchApi->federated_search: #{e}"
end
```

#### Using the federated_search_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<FederatedSearch200Response>, Integer, Hash)> federated_search_with_http_info(federated_search_request)

```ruby
begin
  # Cross-platform federated search.
  data, status_code, headers = api_instance.federated_search_with_http_info(federated_search_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <FederatedSearch200Response>
rescue Spatio::ApiError => e
  puts "Error when calling SearchApi->federated_search_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **federated_search_request** | [**FederatedSearchRequest**](FederatedSearchRequest.md) |  |  |

### Return type

[**FederatedSearch200Response**](FederatedSearch200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

