# Spatio::LogosApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_domain_logo**](LogosApi.md#get_domain_logo) | **GET** /v1/logos/domain/{domain} | Resolve a domain to its logo URL (CDN-cached 24h). |
| [**get_email_logo**](LogosApi.md#get_email_logo) | **GET** /v1/logos/email/{email} | Resolve an email address to its domain logo URL. |
| [**get_logos_batch**](LogosApi.md#get_logos_batch) | **POST** /v1/logos/batch | Batch-resolve a list of domains/emails to logo URLs in one call. |


## get_domain_logo

> <GetDomainLogo200Response> get_domain_logo(domain)

Resolve a domain to its logo URL (CDN-cached 24h).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::LogosApi.new
domain = 'domain_example' # String | 

begin
  # Resolve a domain to its logo URL (CDN-cached 24h).
  result = api_instance.get_domain_logo(domain)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_domain_logo: #{e}"
end
```

#### Using the get_domain_logo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDomainLogo200Response>, Integer, Hash)> get_domain_logo_with_http_info(domain)

```ruby
begin
  # Resolve a domain to its logo URL (CDN-cached 24h).
  data, status_code, headers = api_instance.get_domain_logo_with_http_info(domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDomainLogo200Response>
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_domain_logo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |

### Return type

[**GetDomainLogo200Response**](GetDomainLogo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_email_logo

> Hash&lt;String, Object&gt; get_email_logo(email)

Resolve an email address to its domain logo URL.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::LogosApi.new
email = 'email_example' # String | 

begin
  # Resolve an email address to its domain logo URL.
  result = api_instance.get_email_logo(email)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_email_logo: #{e}"
end
```

#### Using the get_email_logo_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_email_logo_with_http_info(email)

```ruby
begin
  # Resolve an email address to its domain logo URL.
  data, status_code, headers = api_instance.get_email_logo_with_http_info(email)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_email_logo_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_logos_batch

> Hash&lt;String, Object&gt; get_logos_batch(request_body)

Batch-resolve a list of domains/emails to logo URLs in one call.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::LogosApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Batch-resolve a list of domains/emails to logo URLs in one call.
  result = api_instance.get_logos_batch(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_logos_batch: #{e}"
end
```

#### Using the get_logos_batch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_logos_batch_with_http_info(request_body)

```ruby
begin
  # Batch-resolve a list of domains/emails to logo URLs in one call.
  data, status_code, headers = api_instance.get_logos_batch_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling LogosApi->get_logos_batch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

