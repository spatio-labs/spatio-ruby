# Spatio::CalendarProviderInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Stable provider id (e.g. &#x60;google-calendar&#x60;, &#x60;native-calendar&#x60;). |  |
| **name** | **String** |  |  |
| **display_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **is_system** | **Boolean** | &#x60;true&#x60; for built-in providers (the native calendar). | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CalendarProviderInfo.new(
  id: null,
  name: null,
  display_name: null,
  description: null,
  is_system: null
)
```

