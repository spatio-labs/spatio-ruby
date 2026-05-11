# Spatio::SlidesApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_presentation**](SlidesApi.md#create_presentation) | **POST** /v1/slides | Create a presentation. |
| [**create_slide**](SlidesApi.md#create_slide) | **POST** /v1/slides/{id}/slides | Insert a slide. |
| [**create_slide_element**](SlidesApi.md#create_slide_element) | **POST** /v1/slides/{id}/slides/{slideId}/elements | Add a canvas element (text/shape/image) to a slide. |
| [**delete_presentation**](SlidesApi.md#delete_presentation) | **DELETE** /v1/slides/{id} | Delete a presentation. |
| [**delete_slide**](SlidesApi.md#delete_slide) | **DELETE** /v1/slides/{id}/slides/{slideId} | Delete a slide. |
| [**delete_slide_element**](SlidesApi.md#delete_slide_element) | **DELETE** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Delete a slide element. |
| [**disable_presentation_share**](SlidesApi.md#disable_presentation_share) | **DELETE** /v1/slides/{id}/share | Disable public sharing. |
| [**enable_presentation_share**](SlidesApi.md#enable_presentation_share) | **POST** /v1/slides/{id}/share | Enable (or update password on) public sharing. |
| [**export_presentation_pdf**](SlidesApi.md#export_presentation_pdf) | **POST** /v1/slides/{id}/export/pdf | Render the presentation as a PDF. |
| [**export_presentation_pptx**](SlidesApi.md#export_presentation_pptx) | **POST** /v1/slides/{id}/export/pptx | Render the presentation as a PowerPoint (.pptx) file. |
| [**get_presentation**](SlidesApi.md#get_presentation) | **GET** /v1/slides/{id} | Fetch one presentation. |
| [**get_presentation_share_settings**](SlidesApi.md#get_presentation_share_settings) | **GET** /v1/slides/{id}/share | Fetch share settings for a presentation. |
| [**get_public_presentation**](SlidesApi.md#get_public_presentation) | **GET** /public/slides/{token} | Fetch a publicly shared presentation. |
| [**get_slide**](SlidesApi.md#get_slide) | **GET** /v1/slides/{id}/slides/{slideId} | Fetch one slide. |
| [**get_slide_element**](SlidesApi.md#get_slide_element) | **GET** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Fetch one slide element. |
| [**list_presentations**](SlidesApi.md#list_presentations) | **GET** /v1/slides | List presentations across connected accounts. |
| [**list_slide_elements**](SlidesApi.md#list_slide_elements) | **GET** /v1/slides/{id}/slides/{slideId}/elements | List the canvas elements on a slide. |
| [**list_slides_in_presentation**](SlidesApi.md#list_slides_in_presentation) | **GET** /v1/slides/{id}/slides | List slides in a presentation. |
| [**rotate_presentation_share_token**](SlidesApi.md#rotate_presentation_share_token) | **POST** /v1/slides/{id}/share/rotate | Rotate the share token, invalidating outstanding URLs. |
| [**update_presentation**](SlidesApi.md#update_presentation) | **PATCH** /v1/slides/{id} | Update presentation metadata (partial). |
| [**update_slide**](SlidesApi.md#update_slide) | **PATCH** /v1/slides/{id}/slides/{slideId} | Update a slide (partial). |
| [**update_slide_element**](SlidesApi.md#update_slide_element) | **PATCH** /v1/slides/{id}/slides/{slideId}/elements/{elementId} | Update a slide element (partial). |


## create_presentation

> <Presentation> create_presentation(create_presentation_request, opts)

Create a presentation.

Creates a new deck under the target account. Target resolution mirrors `POST /v1/notes` and `/v1/sheets`: body `accountId` → `?accountId=` → body `provider` → `?provider=` → caller's single connected account (errors with `ambiguous_account` otherwise). The new deck is auto-seeded with one blank slide so the renderer has something to display immediately. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
create_presentation_request = Spatio::CreatePresentationRequest.new({title: 'title_example'}) # CreatePresentationRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Create a presentation.
  result = api_instance.create_presentation(create_presentation_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_presentation: #{e}"
end
```

#### Using the create_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Presentation>, Integer, Hash)> create_presentation_with_http_info(create_presentation_request, opts)

```ruby
begin
  # Create a presentation.
  data, status_code, headers = api_instance.create_presentation_with_http_info(create_presentation_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Presentation>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_presentation_request** | [**CreatePresentationRequest**](CreatePresentationRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;). Selects every connected account for the provider. Mutually exclusive with &#x60;accountId&#x60;.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_slide

> <Slide> create_slide(id, create_slide_request, opts)

Insert a slide.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
create_slide_request = Spatio::CreateSlideRequest.new # CreateSlideRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Insert a slide.
  result = api_instance.create_slide(id, create_slide_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_slide: #{e}"
end
```

#### Using the create_slide_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Slide>, Integer, Hash)> create_slide_with_http_info(id, create_slide_request, opts)

```ruby
begin
  # Insert a slide.
  data, status_code, headers = api_instance.create_slide_with_http_info(id, create_slide_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Slide>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_slide_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **create_slide_request** | [**CreateSlideRequest**](CreateSlideRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_slide_element

> <SlideElement> create_slide_element(id, slide_id, create_slide_element_request, opts)

Add a canvas element (text/shape/image) to a slide.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
create_slide_element_request = Spatio::CreateSlideElementRequest.new({element_type: 'element_type_example'}) # CreateSlideElementRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Add a canvas element (text/shape/image) to a slide.
  result = api_instance.create_slide_element(id, slide_id, create_slide_element_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_slide_element: #{e}"
end
```

#### Using the create_slide_element_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SlideElement>, Integer, Hash)> create_slide_element_with_http_info(id, slide_id, create_slide_element_request, opts)

```ruby
begin
  # Add a canvas element (text/shape/image) to a slide.
  data, status_code, headers = api_instance.create_slide_element_with_http_info(id, slide_id, create_slide_element_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SlideElement>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->create_slide_element_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **create_slide_element_request** | [**CreateSlideElementRequest**](CreateSlideElementRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_presentation

> <SuccessFlag> delete_presentation(id, opts)

Delete a presentation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a presentation.
  result = api_instance.delete_presentation(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_presentation: #{e}"
end
```

#### Using the delete_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_presentation_with_http_info(id, opts)

```ruby
begin
  # Delete a presentation.
  data, status_code, headers = api_instance.delete_presentation_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_slide

> <SuccessFlag> delete_slide(id, slide_id, opts)

Delete a slide.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a slide.
  result = api_instance.delete_slide(id, slide_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_slide: #{e}"
end
```

#### Using the delete_slide_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_slide_with_http_info(id, slide_id, opts)

```ruby
begin
  # Delete a slide.
  data, status_code, headers = api_instance.delete_slide_with_http_info(id, slide_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_slide_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_slide_element

> <SuccessFlag> delete_slide_element(id, slide_id, element_id, opts)

Delete a slide element.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
element_id = 'element_id_example' # String | Slide-element id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Delete a slide element.
  result = api_instance.delete_slide_element(id, slide_id, element_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_slide_element: #{e}"
end
```

#### Using the delete_slide_element_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuccessFlag>, Integer, Hash)> delete_slide_element_with_http_info(id, slide_id, element_id, opts)

```ruby
begin
  # Delete a slide element.
  data, status_code, headers = api_instance.delete_slide_element_with_http_info(id, slide_id, element_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuccessFlag>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->delete_slide_element_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **element_id** | **String** | Slide-element id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SuccessFlag**](SuccessFlag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## disable_presentation_share

> disable_presentation_share(id, opts)

Disable public sharing.

Owner-only. Subsequent public viewer requests 404.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Disable public sharing.
  api_instance.disable_presentation_share(id, opts)
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->disable_presentation_share: #{e}"
end
```

#### Using the disable_presentation_share_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> disable_presentation_share_with_http_info(id, opts)

```ruby
begin
  # Disable public sharing.
  data, status_code, headers = api_instance.disable_presentation_share_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->disable_presentation_share_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## enable_presentation_share

> <ShareSettings> enable_presentation_share(id, opts)

Enable (or update password on) public sharing.

Owner-only. With `setPassword: false` (or empty body), flips the deck public without changing the password. With `setPassword: true`, applies `password` (empty clears). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  enable_share_request: Spatio::EnableShareRequest.new # EnableShareRequest | 
}

begin
  # Enable (or update password on) public sharing.
  result = api_instance.enable_presentation_share(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->enable_presentation_share: #{e}"
end
```

#### Using the enable_presentation_share_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> enable_presentation_share_with_http_info(id, opts)

```ruby
begin
  # Enable (or update password on) public sharing.
  data, status_code, headers = api_instance.enable_presentation_share_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->enable_presentation_share_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **enable_share_request** | [**EnableShareRequest**](EnableShareRequest.md) |  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_presentation_pdf

> File export_presentation_pdf(id, opts)

Render the presentation as a PDF.

Proxies to the Spatio export sidecar (Playwright). Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PDF binary     (`application/pdf`).   - `r2` — uploads the rendered PDF to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured (dev fallback to the client-side exporter). 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  storage: 'stream', # String | 
  filename: 'filename_example', # String | Sanitized base name for the downloaded PDF.
  export_pdf_request: Spatio::ExportPDFRequest.new # ExportPDFRequest | 
}

begin
  # Render the presentation as a PDF.
  result = api_instance.export_presentation_pdf(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->export_presentation_pdf: #{e}"
end
```

#### Using the export_presentation_pdf_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> export_presentation_pdf_with_http_info(id, opts)

```ruby
begin
  # Render the presentation as a PDF.
  data, status_code, headers = api_instance.export_presentation_pdf_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->export_presentation_pdf_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **storage** | **String** |  | [optional][default to &#39;stream&#39;] |
| **filename** | **String** | Sanitized base name for the downloaded PDF. | [optional] |
| **export_pdf_request** | [**ExportPDFRequest**](ExportPDFRequest.md) |  | [optional] |

### Return type

**File**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/pdf, application/json


## export_presentation_pptx

> File export_presentation_pptx(id, opts)

Render the presentation as a PowerPoint (.pptx) file.

Proxies to the Spatio export sidecar (Playwright + pptxgenjs). Each slide is screenshotted at 2× device-pixel ratio and wrapped into a PowerPoint .pptx as a full-bleed image. Visual fidelity is preserved exactly — what renders in Spatio renders identically in PowerPoint, Keynote, Google Slides — at the cost of in-PowerPoint editability of slide content. Users edit slide content back in Spatio (the source of truth), not inside PowerPoint.  Two response modes selected via `?storage=`:    - `stream` (default) — response body is the PPTX binary     (`application/vnd.openxmlformats-officedocument.presentationml.presentation`).   - `r2` — uploads the rendered PPTX to R2 storage and returns     a JSON envelope with a 24-hour signed URL.  Returns `503 Service Unavailable` when the export sidecar is not configured. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  storage: 'stream', # String | 
  filename: 'filename_example', # String | Sanitized base name for the downloaded PPTX.
  export_pdf_request: Spatio::ExportPDFRequest.new # ExportPDFRequest | 
}

begin
  # Render the presentation as a PowerPoint (.pptx) file.
  result = api_instance.export_presentation_pptx(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->export_presentation_pptx: #{e}"
end
```

#### Using the export_presentation_pptx_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(File, Integer, Hash)> export_presentation_pptx_with_http_info(id, opts)

```ruby
begin
  # Render the presentation as a PowerPoint (.pptx) file.
  data, status_code, headers = api_instance.export_presentation_pptx_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => File
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->export_presentation_pptx_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |
| **storage** | **String** |  | [optional][default to &#39;stream&#39;] |
| **filename** | **String** | Sanitized base name for the downloaded PPTX. | [optional] |
| **export_pdf_request** | [**ExportPDFRequest**](ExportPDFRequest.md) |  | [optional] |

### Return type

**File**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/vnd.openxmlformats-officedocument.presentationml.presentation, application/json


## get_presentation

> <Presentation> get_presentation(id, opts)

Fetch one presentation.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one presentation.
  result = api_instance.get_presentation(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_presentation: #{e}"
end
```

#### Using the get_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Presentation>, Integer, Hash)> get_presentation_with_http_info(id, opts)

```ruby
begin
  # Fetch one presentation.
  data, status_code, headers = api_instance.get_presentation_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Presentation>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_presentation_share_settings

> <ShareSettings> get_presentation_share_settings(id, opts)

Fetch share settings for a presentation.

Owner-only. Mirror of `GET /v1/notes/{id}/share` — same shape, same fields. Returns the current public-share configuration, including the share token and computed public viewer URL when the deck is currently public. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch share settings for a presentation.
  result = api_instance.get_presentation_share_settings(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_presentation_share_settings: #{e}"
end
```

#### Using the get_presentation_share_settings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> get_presentation_share_settings_with_http_info(id, opts)

```ruby
begin
  # Fetch share settings for a presentation.
  data, status_code, headers = api_instance.get_presentation_share_settings_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_presentation_share_settings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_public_presentation

> Hash&lt;String, Object&gt; get_public_presentation(token, opts)

Fetch a publicly shared presentation.

Unauthenticated. Mirror of `GET /public/notes/{token}`. The share token is the credential. For password-protected decks the password is supplied via `?password=`; the response distinguishes \"no password supplied\" from \"wrong password\" so the viewer can render the right prompt. Unknown tokens and disabled-share decks both return `404` to prevent enumeration. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'

api_instance = Spatio::SlidesApi.new
token = 'token_example' # String | Opaque public-share token.
opts = {
  password: 'password_example' # String | Optional viewer password.
}

begin
  # Fetch a publicly shared presentation.
  result = api_instance.get_public_presentation(token, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_public_presentation: #{e}"
end
```

#### Using the get_public_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_public_presentation_with_http_info(token, opts)

```ruby
begin
  # Fetch a publicly shared presentation.
  data, status_code, headers = api_instance.get_public_presentation_with_http_info(token, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_public_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | Opaque public-share token. |  |
| **password** | **String** | Optional viewer password. | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_slide

> <Slide> get_slide(id, slide_id, opts)

Fetch one slide.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one slide.
  result = api_instance.get_slide(id, slide_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_slide: #{e}"
end
```

#### Using the get_slide_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Slide>, Integer, Hash)> get_slide_with_http_info(id, slide_id, opts)

```ruby
begin
  # Fetch one slide.
  data, status_code, headers = api_instance.get_slide_with_http_info(id, slide_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Slide>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_slide_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_slide_element

> <SlideElement> get_slide_element(id, slide_id, element_id, opts)

Fetch one slide element.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
element_id = 'element_id_example' # String | Slide-element id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Fetch one slide element.
  result = api_instance.get_slide_element(id, slide_id, element_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_slide_element: #{e}"
end
```

#### Using the get_slide_element_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SlideElement>, Integer, Hash)> get_slide_element_with_http_info(id, slide_id, element_id, opts)

```ruby
begin
  # Fetch one slide element.
  data, status_code, headers = api_instance.get_slide_element_with_http_info(id, slide_id, element_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SlideElement>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->get_slide_element_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **element_id** | **String** | Slide-element id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_presentations

> <PresentationListEnvelope> list_presentations(opts)

List presentations across connected accounts.

Fan-out list. Returns every presentation visible to the caller across every connected slides provider. Pass `?accountId=` or `?provider=` to scope to a single source. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  provider: 'provider_example', # String | Provider id (e.g. `native-notes`, `notion`). Selects every connected account for the provider. Mutually exclusive with `accountId`. 
  x_workspace_id: 'x_workspace_id_example', # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
  limit: 56, # Integer | 
  offset: 56 # Integer | 
}

begin
  # List presentations across connected accounts.
  result = api_instance.list_presentations(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_presentations: #{e}"
end
```

#### Using the list_presentations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PresentationListEnvelope>, Integer, Hash)> list_presentations_with_http_info(opts)

```ruby
begin
  # List presentations across connected accounts.
  data, status_code, headers = api_instance.list_presentations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PresentationListEnvelope>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_presentations_with_http_info: #{e}"
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

[**PresentationListEnvelope**](PresentationListEnvelope.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_slide_elements

> <SlideElementList> list_slide_elements(id, slide_id, opts)

List the canvas elements on a slide.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # List the canvas elements on a slide.
  result = api_instance.list_slide_elements(id, slide_id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_slide_elements: #{e}"
end
```

#### Using the list_slide_elements_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SlideElementList>, Integer, Hash)> list_slide_elements_with_http_info(id, slide_id, opts)

```ruby
begin
  # List the canvas elements on a slide.
  data, status_code, headers = api_instance.list_slide_elements_with_http_info(id, slide_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SlideElementList>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_slide_elements_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SlideElementList**](SlideElementList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_slides_in_presentation

> <SlideList> list_slides_in_presentation(id, opts)

List slides in a presentation.

Single-account list. Returns slides in the order set by their `position` field. 

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # List slides in a presentation.
  result = api_instance.list_slides_in_presentation(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_slides_in_presentation: #{e}"
end
```

#### Using the list_slides_in_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SlideList>, Integer, Hash)> list_slides_in_presentation_with_http_info(id, opts)

```ruby
begin
  # List slides in a presentation.
  data, status_code, headers = api_instance.list_slides_in_presentation_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SlideList>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->list_slides_in_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SlideList**](SlideList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## rotate_presentation_share_token

> <ShareSettings> rotate_presentation_share_token(id, opts)

Rotate the share token, invalidating outstanding URLs.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Rotate the share token, invalidating outstanding URLs.
  result = api_instance.rotate_presentation_share_token(id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->rotate_presentation_share_token: #{e}"
end
```

#### Using the rotate_presentation_share_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ShareSettings>, Integer, Hash)> rotate_presentation_share_token_with_http_info(id, opts)

```ruby
begin
  # Rotate the share token, invalidating outstanding URLs.
  data, status_code, headers = api_instance.rotate_presentation_share_token_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ShareSettings>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->rotate_presentation_share_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**ShareSettings**](ShareSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_presentation

> <Presentation> update_presentation(id, update_presentation_request, opts)

Update presentation metadata (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
update_presentation_request = Spatio::UpdatePresentationRequest.new # UpdatePresentationRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update presentation metadata (partial).
  result = api_instance.update_presentation(id, update_presentation_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_presentation: #{e}"
end
```

#### Using the update_presentation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Presentation>, Integer, Hash)> update_presentation_with_http_info(id, update_presentation_request, opts)

```ruby
begin
  # Update presentation metadata (partial).
  data, status_code, headers = api_instance.update_presentation_with_http_info(id, update_presentation_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Presentation>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_presentation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **update_presentation_request** | [**UpdatePresentationRequest**](UpdatePresentationRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Presentation**](Presentation.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_slide

> <Slide> update_slide(id, slide_id, update_slide_request, opts)

Update a slide (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
update_slide_request = Spatio::UpdateSlideRequest.new # UpdateSlideRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a slide (partial).
  result = api_instance.update_slide(id, slide_id, update_slide_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_slide: #{e}"
end
```

#### Using the update_slide_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Slide>, Integer, Hash)> update_slide_with_http_info(id, slide_id, update_slide_request, opts)

```ruby
begin
  # Update a slide (partial).
  data, status_code, headers = api_instance.update_slide_with_http_info(id, slide_id, update_slide_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Slide>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_slide_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **update_slide_request** | [**UpdateSlideRequest**](UpdateSlideRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**Slide**](Slide.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_slide_element

> <SlideElement> update_slide_element(id, slide_id, element_id, update_slide_element_request, opts)

Update a slide element (partial).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::SlidesApi.new
id = 'id_example' # String | Presentation id.
slide_id = 'slide_id_example' # String | Slide id within the presentation.
element_id = 'element_id_example' # String | Slide-element id.
update_slide_element_request = Spatio::UpdateSlideElementRequest.new # UpdateSlideElementRequest | 
opts = {
  account_id: 'account_id_example', # String | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with `provider`. If omitted on a list endpoint the call fans out across every connected account. 
  x_workspace_id: 'x_workspace_id_example' # String | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly. 
}

begin
  # Update a slide element (partial).
  result = api_instance.update_slide_element(id, slide_id, element_id, update_slide_element_request, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_slide_element: #{e}"
end
```

#### Using the update_slide_element_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SlideElement>, Integer, Hash)> update_slide_element_with_http_info(id, slide_id, element_id, update_slide_element_request, opts)

```ruby
begin
  # Update a slide element (partial).
  data, status_code, headers = api_instance.update_slide_element_with_http_info(id, slide_id, element_id, update_slide_element_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SlideElement>
rescue Spatio::ApiError => e
  puts "Error when calling SlidesApi->update_slide_element_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Presentation id. |  |
| **slide_id** | **String** | Slide id within the presentation. |  |
| **element_id** | **String** | Slide-element id. |  |
| **update_slide_element_request** | [**UpdateSlideElementRequest**](UpdateSlideElementRequest.md) |  |  |
| **account_id** | **String** | Connected-account row id. Selects which provider account this request targets when more than one is connected. Mutually exclusive with &#x60;provider&#x60;. If omitted on a list endpoint the call fans out across every connected account.  | [optional] |
| **x_workspace_id** | **String** | Workspace scope for unscoped tokens. Workspace-scoped PATs and OAuth tokens carry this implicitly; for session/JWT auth without a scoped PAT, pass it explicitly.  | [optional] |

### Return type

[**SlideElement**](SlideElement.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

