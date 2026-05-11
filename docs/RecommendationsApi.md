# Spatio::RecommendationsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_recommendation**](RecommendationsApi.md#delete_recommendation) | **DELETE** /v1/recommendations/{id} | Delete a recommendation (hard delete; status-update is preferred). |
| [**get_recommendation**](RecommendationsApi.md#get_recommendation) | **GET** /v1/recommendations/{id} | Fetch one recommendation. |
| [**list_recommendations**](RecommendationsApi.md#list_recommendations) | **GET** /v1/recommendations | List recommendations for a workspace. |
| [**propose_recommendation**](RecommendationsApi.md#propose_recommendation) | **POST** /v1/recommendations | Agent-side propose endpoint (the &#x60;spatio_recommendations propose&#x60; MCP tool calls this). |
| [**update_recommendation_status**](RecommendationsApi.md#update_recommendation_status) | **PATCH** /v1/recommendations/{id}/status | Accept or dismiss a recommendation. |


## delete_recommendation

> delete_recommendation(id)

Delete a recommendation (hard delete; status-update is preferred).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecommendationsApi.new
id = 'id_example' # String | 

begin
  # Delete a recommendation (hard delete; status-update is preferred).
  api_instance.delete_recommendation(id)
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->delete_recommendation: #{e}"
end
```

#### Using the delete_recommendation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_recommendation_with_http_info(id)

```ruby
begin
  # Delete a recommendation (hard delete; status-update is preferred).
  data, status_code, headers = api_instance.delete_recommendation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->delete_recommendation_with_http_info: #{e}"
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


## get_recommendation

> <Recommendation> get_recommendation(id)

Fetch one recommendation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecommendationsApi.new
id = 'id_example' # String | 

begin
  # Fetch one recommendation.
  result = api_instance.get_recommendation(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->get_recommendation: #{e}"
end
```

#### Using the get_recommendation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Recommendation>, Integer, Hash)> get_recommendation_with_http_info(id)

```ruby
begin
  # Fetch one recommendation.
  data, status_code, headers = api_instance.get_recommendation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Recommendation>
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->get_recommendation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_recommendations

> <RecommendationListResponse> list_recommendations(opts)

List recommendations for a workspace.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecommendationsApi.new
opts = {
  workspace_id: 'workspace_id_example', # String | 
  status: 'status_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List recommendations for a workspace.
  result = api_instance.list_recommendations(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->list_recommendations: #{e}"
end
```

#### Using the list_recommendations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecommendationListResponse>, Integer, Hash)> list_recommendations_with_http_info(opts)

```ruby
begin
  # List recommendations for a workspace.
  data, status_code, headers = api_instance.list_recommendations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecommendationListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->list_recommendations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **workspace_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**RecommendationListResponse**](RecommendationListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## propose_recommendation

> <Recommendation> propose_recommendation(propose_recommendation_request)

Agent-side propose endpoint (the `spatio_recommendations propose` MCP tool calls this).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecommendationsApi.new
propose_recommendation_request = Spatio::ProposeRecommendationRequest.new({kind: 'kind_example'}) # ProposeRecommendationRequest | 

begin
  # Agent-side propose endpoint (the `spatio_recommendations propose` MCP tool calls this).
  result = api_instance.propose_recommendation(propose_recommendation_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->propose_recommendation: #{e}"
end
```

#### Using the propose_recommendation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Recommendation>, Integer, Hash)> propose_recommendation_with_http_info(propose_recommendation_request)

```ruby
begin
  # Agent-side propose endpoint (the `spatio_recommendations propose` MCP tool calls this).
  data, status_code, headers = api_instance.propose_recommendation_with_http_info(propose_recommendation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Recommendation>
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->propose_recommendation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **propose_recommendation_request** | [**ProposeRecommendationRequest**](ProposeRecommendationRequest.md) |  |  |

### Return type

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_recommendation_status

> <Recommendation> update_recommendation_status(id, update_recommendation_status_request)

Accept or dismiss a recommendation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RecommendationsApi.new
id = 'id_example' # String | 
update_recommendation_status_request = Spatio::UpdateRecommendationStatusRequest.new({status: 'accepted'}) # UpdateRecommendationStatusRequest | 

begin
  # Accept or dismiss a recommendation.
  result = api_instance.update_recommendation_status(id, update_recommendation_status_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->update_recommendation_status: #{e}"
end
```

#### Using the update_recommendation_status_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Recommendation>, Integer, Hash)> update_recommendation_status_with_http_info(id, update_recommendation_status_request)

```ruby
begin
  # Accept or dismiss a recommendation.
  data, status_code, headers = api_instance.update_recommendation_status_with_http_info(id, update_recommendation_status_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Recommendation>
rescue Spatio::ApiError => e
  puts "Error when calling RecommendationsApi->update_recommendation_status_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_recommendation_status_request** | [**UpdateRecommendationStatusRequest**](UpdateRecommendationStatusRequest.md) |  |  |

### Return type

[**Recommendation**](Recommendation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

