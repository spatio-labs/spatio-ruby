# Spatio::ContactsApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**assign_contact_category**](ContactsApi.md#assign_contact_category) | **POST** /v1/contacts/{id}/categories | Assign a category to a contact. |
| [**create_contact**](ContactsApi.md#create_contact) | **POST** /v1/contacts | Create a contact. |
| [**create_contact_category**](ContactsApi.md#create_contact_category) | **POST** /v1/contacts/categories | Create a contact category. |
| [**delete_contact**](ContactsApi.md#delete_contact) | **DELETE** /v1/contacts/{id} | Delete a contact. |
| [**delete_contact_category**](ContactsApi.md#delete_contact_category) | **DELETE** /v1/contacts/categories/{id} | Delete a category. |
| [**get_contact**](ContactsApi.md#get_contact) | **GET** /v1/contacts/{id} | Fetch a contact. |
| [**list_contact_categories**](ContactsApi.md#list_contact_categories) | **GET** /v1/contacts/categories | List contact categories. Requires &#x60;organization_id&#x60; query param. |
| [**list_contact_providers**](ContactsApi.md#list_contact_providers) | **GET** /v1/contacts/providers | List supported contact providers (native + OAuth-connected). |
| [**list_contacts**](ContactsApi.md#list_contacts) | **GET** /v1/contacts | List the caller&#39;s contacts (across providers). |
| [**unassign_contact_category**](ContactsApi.md#unassign_contact_category) | **DELETE** /v1/contacts/{id}/categories/{categoryId} | Remove a category from a contact. |
| [**update_contact**](ContactsApi.md#update_contact) | **PATCH** /v1/contacts/{id} | Update a contact. |
| [**update_contact_category**](ContactsApi.md#update_contact_category) | **PATCH** /v1/contacts/categories/{id} | Update a category. |


## assign_contact_category

> assign_contact_category(id, assign_contact_category_request)

Assign a category to a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 
assign_contact_category_request = Spatio::AssignContactCategoryRequest.new({category_id: 'category_id_example'}) # AssignContactCategoryRequest | 

begin
  # Assign a category to a contact.
  api_instance.assign_contact_category(id, assign_contact_category_request)
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->assign_contact_category: #{e}"
end
```

#### Using the assign_contact_category_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> assign_contact_category_with_http_info(id, assign_contact_category_request)

```ruby
begin
  # Assign a category to a contact.
  data, status_code, headers = api_instance.assign_contact_category_with_http_info(id, assign_contact_category_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->assign_contact_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **assign_contact_category_request** | [**AssignContactCategoryRequest**](AssignContactCategoryRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_contact

> <Contact> create_contact(create_contact_request)

Create a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
create_contact_request = Spatio::CreateContactRequest.new # CreateContactRequest | 

begin
  # Create a contact.
  result = api_instance.create_contact(create_contact_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->create_contact: #{e}"
end
```

#### Using the create_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> create_contact_with_http_info(create_contact_request)

```ruby
begin
  # Create a contact.
  data, status_code, headers = api_instance.create_contact_with_http_info(create_contact_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->create_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_contact_request** | [**CreateContactRequest**](CreateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_contact_category

> <ContactCategory> create_contact_category(create_contact_category_request)

Create a contact category.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
create_contact_category_request = Spatio::CreateContactCategoryRequest.new({name: 'name_example'}) # CreateContactCategoryRequest | 

begin
  # Create a contact category.
  result = api_instance.create_contact_category(create_contact_category_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->create_contact_category: #{e}"
end
```

#### Using the create_contact_category_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactCategory>, Integer, Hash)> create_contact_category_with_http_info(create_contact_category_request)

```ruby
begin
  # Create a contact category.
  data, status_code, headers = api_instance.create_contact_category_with_http_info(create_contact_category_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactCategory>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->create_contact_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_contact_category_request** | [**CreateContactCategoryRequest**](CreateContactCategoryRequest.md) |  |  |

### Return type

[**ContactCategory**](ContactCategory.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_contact

> delete_contact(id)

Delete a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 

begin
  # Delete a contact.
  api_instance.delete_contact(id)
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->delete_contact: #{e}"
end
```

#### Using the delete_contact_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_contact_with_http_info(id)

```ruby
begin
  # Delete a contact.
  data, status_code, headers = api_instance.delete_contact_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->delete_contact_with_http_info: #{e}"
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


## delete_contact_category

> delete_contact_category(id)

Delete a category.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 

begin
  # Delete a category.
  api_instance.delete_contact_category(id)
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->delete_contact_category: #{e}"
end
```

#### Using the delete_contact_category_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_contact_category_with_http_info(id)

```ruby
begin
  # Delete a category.
  data, status_code, headers = api_instance.delete_contact_category_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->delete_contact_category_with_http_info: #{e}"
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


## get_contact

> <Contact> get_contact(id)

Fetch a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 

begin
  # Fetch a contact.
  result = api_instance.get_contact(id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->get_contact: #{e}"
end
```

#### Using the get_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> get_contact_with_http_info(id)

```ruby
begin
  # Fetch a contact.
  data, status_code, headers = api_instance.get_contact_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->get_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_contact_categories

> <ContactCategoryListResponse> list_contact_categories(organization_id)

List contact categories. Requires `organization_id` query param.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
organization_id = 'organization_id_example' # String | 

begin
  # List contact categories. Requires `organization_id` query param.
  result = api_instance.list_contact_categories(organization_id)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contact_categories: #{e}"
end
```

#### Using the list_contact_categories_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactCategoryListResponse>, Integer, Hash)> list_contact_categories_with_http_info(organization_id)

```ruby
begin
  # List contact categories. Requires `organization_id` query param.
  data, status_code, headers = api_instance.list_contact_categories_with_http_info(organization_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactCategoryListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contact_categories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **organization_id** | **String** |  |  |

### Return type

[**ContactCategoryListResponse**](ContactCategoryListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_contact_providers

> <ContactProviderListResponse> list_contact_providers

List supported contact providers (native + OAuth-connected).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new

begin
  # List supported contact providers (native + OAuth-connected).
  result = api_instance.list_contact_providers
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contact_providers: #{e}"
end
```

#### Using the list_contact_providers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactProviderListResponse>, Integer, Hash)> list_contact_providers_with_http_info

```ruby
begin
  # List supported contact providers (native + OAuth-connected).
  data, status_code, headers = api_instance.list_contact_providers_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactProviderListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contact_providers_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ContactProviderListResponse**](ContactProviderListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_contacts

> <ContactListResponse> list_contacts(opts)

List the caller's contacts (across providers).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
opts = {
  limit: 56, # Integer | 
  provider: 'provider_example', # String | 
  search: 'search_example' # String | 
}

begin
  # List the caller's contacts (across providers).
  result = api_instance.list_contacts(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contacts: #{e}"
end
```

#### Using the list_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactListResponse>, Integer, Hash)> list_contacts_with_http_info(opts)

```ruby
begin
  # List the caller's contacts (across providers).
  data, status_code, headers = api_instance.list_contacts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactListResponse>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->list_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **search** | **String** |  | [optional] |

### Return type

[**ContactListResponse**](ContactListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## unassign_contact_category

> unassign_contact_category(id, category_id)

Remove a category from a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 
category_id = 'category_id_example' # String | 

begin
  # Remove a category from a contact.
  api_instance.unassign_contact_category(id, category_id)
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->unassign_contact_category: #{e}"
end
```

#### Using the unassign_contact_category_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> unassign_contact_category_with_http_info(id, category_id)

```ruby
begin
  # Remove a category from a contact.
  data, status_code, headers = api_instance.unassign_contact_category_with_http_info(id, category_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->unassign_contact_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **category_id** | **String** |  |  |

### Return type

nil (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_contact

> <Contact> update_contact(id, update_contact_request)

Update a contact.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 
update_contact_request = Spatio::UpdateContactRequest.new # UpdateContactRequest | 

begin
  # Update a contact.
  result = api_instance.update_contact(id, update_contact_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->update_contact: #{e}"
end
```

#### Using the update_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Contact>, Integer, Hash)> update_contact_with_http_info(id, update_contact_request)

```ruby
begin
  # Update a contact.
  data, status_code, headers = api_instance.update_contact_with_http_info(id, update_contact_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Contact>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->update_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_contact_request** | [**UpdateContactRequest**](UpdateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_contact_category

> <ContactCategory> update_contact_category(id, update_contact_category_request)

Update a category.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::ContactsApi.new
id = 'id_example' # String | 
update_contact_category_request = Spatio::UpdateContactCategoryRequest.new # UpdateContactCategoryRequest | 

begin
  # Update a category.
  result = api_instance.update_contact_category(id, update_contact_category_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->update_contact_category: #{e}"
end
```

#### Using the update_contact_category_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ContactCategory>, Integer, Hash)> update_contact_category_with_http_info(id, update_contact_category_request)

```ruby
begin
  # Update a category.
  data, status_code, headers = api_instance.update_contact_category_with_http_info(id, update_contact_category_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ContactCategory>
rescue Spatio::ApiError => e
  puts "Error when calling ContactsApi->update_contact_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_contact_category_request** | [**UpdateContactCategoryRequest**](UpdateContactCategoryRequest.md) |  |  |

### Return type

[**ContactCategory**](ContactCategory.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

