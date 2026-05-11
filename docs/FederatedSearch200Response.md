# Spatio::FederatedSearch200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **items** | [**Array&lt;FederatedSearch200ResponseItemsInner&gt;**](FederatedSearch200ResponseItemsInner.md) |  |  |
| **next_page_tokens** | **Hash&lt;String, String&gt;** |  | [optional] |
| **per_platform** | [**Hash&lt;String, FederatedSearch200ResponsePerPlatformValue&gt;**](FederatedSearch200ResponsePerPlatformValue.md) |  |  |
| **errors** | **Hash&lt;String, String&gt;** | Per-platform errors. Other platforms still return results. | [optional] |
| **total_returned** | **Integer** |  |  |
| **took** | **String** | Aggregate wall-clock time for the fan-out, e.g. \&quot;120ms\&quot;. |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::FederatedSearch200Response.new(
  items: null,
  next_page_tokens: null,
  per_platform: null,
  errors: null,
  total_returned: null,
  took: null
)
```

